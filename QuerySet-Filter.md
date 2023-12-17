Making queries - 2 / QuerySet - Filter 
========================================================
* Return only the records where the firstname is 'Emil':

```shell
mydata = Member.objects.filter(firstname='Emil').values()
```

* AND
* Example: Return records where lastname is "Refsnes" and id is 2:
```shell
mydata = Member.objects.filter(lastname='Refsnes', id=2).values()
```

* OR
* Example: Return records where firstname is 
* either "Emil" or Tobias":
```shell
mydata = Member.objects.filter(firstname='Emil').values() | Member.objects.filter(firstname='Tobias').values()

* Q expressions:
* Example: Return records where firstname is 
* either "Emil" or Tobias":
```python3
from django.http import HttpResponse
from django.template import loader
from .models import Member
from django.db.models import Q

def testing(request):
  mydata = Member.objects.filter(Q(firstname='Emil') | Q(firstname='Tobias')).values()
  template = loader.get_template('template.html')
  context = {
    'mymembers': mydata,
  }
  return HttpResponse(template.render(context, request))
```

* Field Lookups
* Example: Use the __startswith keyword:

```shell
.filter(firstname__startswith='L');
```

* Field Lookups Syntax
* Example: Return the records where firstname 
* starts with the letter 'L': 
```shell
mydata = Member.objects.filter(firstname__startswith='L').values()
```

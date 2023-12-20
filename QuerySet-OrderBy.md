Making queries - 2 / QuerySet - Order By
========================================================

* Example: Order the result alphabetically by firstname:

```shell
mydata = Member.objects.all().order_by('firstname').values()
```

* Descending Order
* Example: Order the result firstname descending:

```shell
mydata = Member.objects.all().order_by('-firstname').values()
```

* Multiple Order Bys
* Example: Order the result first by lastname ascending, 
* then descending on id:

```shell
mydata = Member.objects.all().order_by('lastname', '-id').values()
```

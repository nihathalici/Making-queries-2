Making queries - 2 / QuerySet - Order By
========================================================

* Example: Order the result alphabetically by firstname:

```shell
mydata = Member.objects.all().order_by('firstname').values()
```

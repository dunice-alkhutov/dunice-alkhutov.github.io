---
layout:     post
title:      "Happy new year!"
subtitle:   "My congrats."
date:       2017-01-01 12:00:00
author:     "Alexey A."
header-img: "img/post-bg-01.jpg"
---
# Happy New Year!

I hope this year presents to you all the best!

_django_forms.py_
```python
def _clean_fields(self):
    for name, field in self.fields.items():
        # value_from_datadict() gets the data from the data dictionaries.
        # Each widget type knows how to retrieve its own data, because some
        # widgets split data over several HTML fields.
        print("*****")
        print("name",name)
        print("field",field)
        ...
            self.cleaned_data[name] = value
            print("try to check %s" % name)
            print("self.cleaned_data",self.cleaned_data)
            if hasattr(self, 'clean_%s' % name):
                value = getattr(self, 'clean_%s' % name)()
                self.cleaned_data[name] = value
            print("end try")
        except ValidationError as e:
            self.add_error(name, e)
```
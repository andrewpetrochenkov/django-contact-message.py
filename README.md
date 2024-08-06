### Installation
```bash
$ pip install django-contact-message
```

#### `settings.py`
```python
INSTALLED_APPS+=['django_contact_message']
```

### Features
+   database
+   admin
+   print message if `settings.DEBUG==True`

### Models
model|table|columns/fields
-|-|-
`Command`|`django_command_message`|`id`,`command`,`message`,`created_at`

### Examples
`CommandMessageMixin`
```python
from django_command_message.mixins import CommandMessageMixin

class Command(CommandMessageMixin,BaseCommand):
    def handle(self, *args, **options):
        self.message('message')
```

`Message` model
```python
from django_command_message.models import Message

Message(command='name',message="message").save()
```


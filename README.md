# django-boilerplate

This is my django-boilerplate, there are many like it but this one is mine. The
point of my boilerplate is to have separate requirements and settings for my
three environments:

 + Production
 + Development
 + Jenkins

Most Django boilerplates have the first two but all lack Jenkins settings and I
really like Jenkins...

## Using Different Settings

The easiest way is to use the `--settings` switch during `runserver`. e.g.
`bin/python manage.py runserver --settings=project.settings.jenkins`

The way you should do it on your production server is by changing this line in
the `manage.py` file:

    os.environ.setdefault("DJANGO_SETTINGS_MODULE", "project.settings.development")

For example set `project.settings.development` to `project.settings.production`
and then you acn simply use `bin/python manage.py runserver` without the
`--settings` switch.

## Build Status

You can check the latest version of django-boilerplate's build status on my
[personal Jenkins server][0]. This lets you if the master branch actually works.
It also lets you know my pep8 and pylint conformance along with my test code
coverage. (See, isn't this cool!)

[0]: http://jenkins.bythewood.me/job/django-boilerplate/

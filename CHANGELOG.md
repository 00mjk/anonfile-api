
# Changelog

## Version 0.2.0 (2021-05-04)

- **IMPORTANT:** This is a major update to the client-facing library interface
  and project infrastructure, see below a small code snippet to help you migrate
  to the newest version of `anonfile`:

```diff
# flat namespace
- from anonfile.anonfile import AnonFile
+ from anonfile import AnonFile

anon = AnonFile('my_token')

# new method names
- upload = anon.upload_file('/home/guest/jims_paperwork.doc')
+ upload = anon.upload('/home/guest/jims_paperwork.doc')

- download = anon.download_file('https://anonfiles.com/9ee1jcu6u9/test_txt')
+ download = anon.download('https://anonfiles.com/9ee1jcu6u9/test_txt')
```

- The return type of the `upload` and `download` method changed to the `ParseResponse`
  dataclass
- Drops support for all third-party servers, i.e. only file up- and downloads to
  anonfiles.com work out of the box
- Reduces all project dependencies to `requests`, `requests_html` and `faker`
- Added doc strings everywhere

## Version 0.1.3 (2021-04-02)

- Added a retry strategy to HTTP requests and updated the `lxml` dependency

## Version 0.1.2 (2020-06-28)

- Changed the URI for the target API's from 'https://example.com/api' to 'https://api.example.com/'.
- Fix bug where hosting website was returning a 404.
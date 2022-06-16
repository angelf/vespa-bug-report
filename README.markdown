
To reproduce the issue:

1. Clone the repro

2. `mvn package && vespa deploy --wait 60 && vespa test tests/systems-tests/default-test.json` - You'll see that the test fails.

3. Comment the following line in services.xml

```
<document type='news' class="com.example.documents.News" bundle="example-app" />
```

4.  `mvn package && vespa deploy --wait 60 && vespa test tests/systems-tests/default-test.json` - You'll see that the test now succeeds.
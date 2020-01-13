# regex

## get params from url

> (?:[&?](?<key>[^?&=]+)=(?<val>[^?&=]*))

```java
       	    private static final String URL_PATTERN = "(?:[&?](?<key>[^?&=]+)=(?<val>[^?&=]*))";
    	    private static final Pattern sPattern = Pattern.compile(URL_PATTERN);

	    Map<String, String> queryParams = new HashMap<>();

            Matcher matcher = sPattern.matcher(url);
            while (matcher.find()) {
                String key = URLDecoder.decode(matcher.group(1));
                Log.v(TAG, "key:" + key);
                String val = URLDecoder.decode(matcher.group(2));
                Log.v(TAG, "val:" + val);
                queryParams.put(key, val);
            }
```

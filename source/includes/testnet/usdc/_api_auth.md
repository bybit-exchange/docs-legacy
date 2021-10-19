# t(:authentication)
<aside class="notice">
t(:auth_aside_key)
</aside>

<aside class="notice">
t(:spot_auth_aside_env)
</aside>

t(:auth_para_privatepublic)

## t(:authenticationparameters)

t(:usdcMethodInfo)


t(:spot_auth_para_recv)

<aside class="warning">
t(:spot_auth_aside_timestamp)
</aside>

## t(:constructingtherequest)

t(:usdc_auth_para_construct1)
t(:auth_para_construct2)

```java
import okhttp3.*;

import javax.crypto.Mac;
import javax.crypto.spec.SecretKeySpec;
import java.io.IOException;
import java.security.InvalidKeyException;
import java.security.NoSuchAlgorithmException;

public class PostExample {
    public static final MediaType JSON = MediaType.get("application/json; charset=utf-8");

    final OkHttpClient client = new OkHttpClient();

    String post(String url, String json, String secret, String apiKey, int recv_window) throws Exception {

        long timeMillis = System.currentTimeMillis();
        RequestBody body = RequestBody.create(json, JSON);
        String sign = sign(json, secret, apiKey, recv_window, timeMillis);
        Request request = new Request.Builder()
                .url(url)
                .post(body)
                .header("X-BAPI-SIGN", sign)
                .header("X-BAPI-API-KEY", apiKey)
                .header("X-BAPI-TIMESTAMP", "" + timeMillis)
                .header("X-BAPI-RECV-WINDOW", "" + recv_window)
                .build();
        try (Response response = client.newCall(request).execute()) {
            return response.body().string();
        }
    }

    public static void main(String[] args) throws IOException {
        PostExample example = new PostExample();

        String url = "http://api.bybit.com/option/usdc/openapi/private/trading/create-order";
        String secret = "xxxxxxxxxxxxxxxxxxxxxxxxxxx";
        String apiKey = "xxxxxxxxxx";
        String json = "{\"outRequestId\":\"021f276a-0a5f-4f35-9859-5f32353ce0ad\",\"symbol\":\"BTC-26NOV21-58000-P\",\"orderType\":\"Limit\",\"side\":\"Buy\",\"orderQty\":\"1\",\"orderPrice\":\"1\",\"timeInForce\":\"GoodTillCancel\",\"placeMode\":1,\"placeType\":1}";
        String response = null;
        int recv_window = 3000;
        try {
            response = example.post(url, json, secret, apiKey, recv_window);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    private static String sign(String json, String secret, String apiKey, int recv_window, long timeMillis) throws NoSuchAlgorithmException, InvalidKeyException {

        Mac sha256_HMAC = Mac.getInstance("HmacSHA256");
        SecretKeySpec secret_key = new SecretKeySpec(secret.getBytes(), "HmacSHA256");
        sha256_HMAC.init(secret_key);

        String s = "" + timeMillis + apiKey + recv_window + json;
        return bytesToHex(sha256_HMAC.doFinal(s.getBytes()));
    }

    private static String bytesToHex(byte[] hash) {
        StringBuffer hexString = new StringBuffer();
        for (int i = 0; i < hash.length; i++) {
            String hex = Integer.toHexString(0xff & hash[i]);
            if (hex.length() == 1) {
                hexString.append('0');
            }
            hexString.append(hex);
        }
        return hexString.toString();
    }
}


```


t(:auth_para_construct3)


<!--
### Examples of the Signature Algorithm

* [C#](https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/example/Encryption.cs)
* [Python](https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/example/Encryption.py)
* [C++](https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/example/Encryption.cpp)
* [Go](https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/example/Encryption.go)
* [PHP](https://github.com/bybit-exchange/bybit-official-api-docs/blob/master/en/example/Encryption.php)
-->


<script>
function copyStringToClipboard (endpoint) {
  var str = document.getElementById(endpoint).innerText;
  // remove whitespace
  var str = str.replace(/ /g,"");
  // Create new element
  var el = document.createElement("textarea");
  // Set value (string to be copied)
  el.value = str;
  // Set non-editable to avoid focus and move outside of view
  el.setAttribute("readonly", "");
  el.style = {position: "absolute", left: "-9999px"};
  document.body.appendChild(el);
  // Select text inside element
  el.select();
  // Copy text to clipboard
  document.execCommand("copy");
  // Remove temporary element
  document.body.removeChild(el);
}
</script>

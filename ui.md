# UI 서버 접속

## 리눅스 또는 맥에서 터미널을 이용한 접속 (Accessing via Terminal on Linux or Mac)

OTP를 설정한 후 GSDC UI 서버에 접속하기 위해서는 두 번의 인증을 수행하여야 합니다.&#x20;

첫번째 인증은 기존과 같이 password 인증을 수행하고, 두번째 인증는 발급 받은 OTP 토큰 인증을 수행하여야 합니다.



첫번째 인증(First Authentication) :

<pre data-overflow="wrap"><code><strong>First Factor: [Enter your regular password here]
</strong></code></pre>



두번째 인증(Second Authentication) :

```
Second Factor: [Enter the OTP code here]
```

\<ex>

```
$> ssh -p [port number] test_ipa@[target UI's hostname]
(test_ipa@[UI]) First Factor: [Enter regular password]
(test_ipa@[UI]) Second Factor: [Enter OTP code]
Last login: [last login details]
[test_ipa@[UI] ~]$
```



## 윈도우에서 MobaXterm을 이용한 접속 (Connecting via MobaXterm on Windows)

OTP를 설정한 후 GSDC UI 서버에 접속하기 위해서는 두 번의 인증을 수행하여야 합니다.&#x20;

첫번째 인증은 기존과 같이 password 인증을 수행하고, 두번째 인증는 발급 받은 OTP 토큰 인증을 수행하여야 합니다.&#x20;



첫번째 인증(First Authentication) :

{% code overflow="wrap" %}
```
First Factor: [Enter regular password here]
```
{% endcode %}



두번째 인증(Second Authentication) :

```
Second Factor: [Enter OTP code here]
```



<예>

<figure><img src=".gitbook/assets/SE-c6700a9b-0f39-4891-ab3c-a066d98dfb96 (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/스크린샷_2023-10-18_오후_6.15.01 (1).png" alt=""><figcaption></figcaption></figure>

## FileZilla를 이용한 접속 (Using FileZilla for Connection)

OTP를 설정한 후 GSDC UI 서버에 접속하기 위해서는 두 번의 인증을 수행하여야 합니다.&#x20;

첫번째 인증은 기존과 같이 password 인증을 수행하고, 두번째 인증는 발급 받은 OTP 토큰 인증을 수행하여야 합니다.&#x20;



첫번째 인증(First Authentication) :

{% code overflow="wrap" %}
```
First Factor: [Enter regular password here]
```
{% endcode %}



두번째 인증(Second Authentication) :

```
Second Factor: [Enter OTP code here]
```



\<ex>

<figure><img src=".gitbook/assets/스크린샷 2023-10-19 오후 5.30.25.png" alt=""><figcaption></figcaption></figure>

⌗ Logon Type 설정은 필히 Interactive 으로 변경하여야 함.





## xshell을 이용한 접속 (Connecting using Xshell)

OTP를 설정한 후 GSDC UI 서버에 접속하기 위해서는 두 번의 인증을 수행하여야 합니다.&#x20;

첫번째 인증은 기존과 같이 password 인증을 수행하고, 두번째 인증는 발급 받은 OTP 토큰 인증을 수행하여야 합니다.



첫번째 인증(First Authentication) :

{% code overflow="wrap" %}
```
First Factor: [Enter regular password here]
```
{% endcode %}



두번째 인증(Second Authentication) :

```
Second Factor: [Enter OTP code here]
```



\<ex>

<figure><img src=".gitbook/assets/스크린샷 2023-10-19 오후 6.04.29.png" alt=""><figcaption></figcaption></figure>

⌗ 사용자 인증에서 방법은 필히 Keyboard Interactive 으로 변경하여야 함.



## 주의사항 (Caution)

* OTP 코드는 시간에 따라 계속 변경됩니다. 따라서 접속 시 마다 새로운 OTP 코드를 사용해야 합니다.
* OTP 인증을 잘못 입력하면 접속이 거부될 수 있습니다. 입력 정보를 정확히 확인한 후 다시 시도해주세요.

## TOAST > TOAST SDK 사용 가이드 > TOAST Logger > Android

## Prerequisites

1\. [Install the TOAST SDK](./getting-started-android)
2\. [TOAST 콘솔](https://console.cloud.toast.com)에서 [Log & Crash Search를 활성화](https://docs.toast.com/ko/Analytics/Log%20&%20Crash%20Search/ko/console-guide/)합니다.
3\. Log & Crash Search에서 [AppKey를 확인](https://docs.toast.com/ko/Analytics/Log%20&%20Crash%20Search/ko/console-guide/#appkey)합니다.

## TOAST Logger SDK 초기화

onCreate() 메서드에서 Logger를 초기화합니다.
Log&Crash Search에서 발급받은 AppKey를 ProjectKey로 설정합니다.

```java
// Initialize Logger
ToastLoggerConfiguration loggerConfiguration = new ToastLoggerConfiguration.Builder()
        .setProjectKey(YOUR_PROJECT_KEY)            // Log & Crash Search AppKey
        .setProjectVersion(YOUR_PROJECT_VERSION)    // App Version
        .build();

ToastLogger.initialize(loggerConfiguration);
```

## 로그 전송하기

TOAST Logger는 5가지 레벨의 로그 전송 함수를 제공합니다.

### 로그 전송 API 명세

```java
// DEBUG 레벨 로그
static void debug(String message);

// INFO 레벨 로그
static void info(String message);

// WARN 레벨 로그
static void warn(String message);

// ERROR 레벨 로그
static void error(String message);

// FATAL 레벨 로그
static void fatal(String message);
```

### 로그 전송 API 사용 예

```java
ToastLogger.warn("TOAST Log & Crash Search!");
```

## UserID 설정하기

UserID를 설정하는 경우 사용자 아이디를 설정할 수 있습니다.
설정한 사용자 아이디는 "UserID" 필드로 Log & Crash Search 콘솔을 통해 손쉽게 필터링하여 조회할 수 있습니다.
UserID를 설정하면 로그 전송 API를 호출할 때마다 설정한 사용자 아이디를 로그와 함께 서버로 전송합니다.

### UserID API 명세

```java
static void setUserId(String userId);
```

### UserID 설정 사용 예

```java
ToastLogger.setUserId("TOAST");
```

## 사용자 정의 필드 설정하기

사용자 정의 원하는 필드를 설정합니다. 
사용자 정의 필드를 설정하면 로그 전송 API를 호출할 때마다 설정한 값을 로그와 함께 서버로 전송합니다.

### setUserField API 명세

```java
static void setUserField(String field, Object value);
```

*  사용자 정의 필드는 "Log & Crash Search 콘솔" > "Log Search 탭"에 "선택한 필드"로 노출되는 값과 동일합니다.  
즉, Log & Crash Search의 커스텀 파라미터와 동일한 것으로 "field"값의 상세한 제약 사항은 [커스텀 필드의 제약사항](http://docs.toast.com/ko/Analytics/Log%20&%20Crash%20Search/ko/api-guide/)에서 확인할 수 있습니다.

#### 커스텀 필드 제약사항

* 이미 [예약된 필드](./log-collector-reserved-fields)는 사용할 수 없습니다.  
예약된 필드는 [커스텀 필드의 제약사항](http://docs.toast.com/ko/Analytics/Log%20&%20Crash%20Search/ko/api-guide/) 항목의 "기본 파라미터"를 확인하세요.
* 필드명은 "A-Z, a-z"로 시작하고 "A-Z, a-z, 0-9, -, _" 문자를 사용할 수 있습니다.
* 필드명 내에 공백은 "\_"로 치환됩니다.

### setUserField 사용 예

```java
ToastLogger.setUserField("nickname", "randy");
```

## 로그 전송 후 추가작업 진행하기

콜백 함수를 등록하면 로그 전송 후 추가 작업을 진행할 수 있습니다.

### setListener API 명세

```java
static void setListener(ToastLoggerListener listener);
```

### setListener 사용 예

```java
ToastLogger.setListener(new ToastLoggerListener() {
    @Override
    public void onSuccess(LogObject log) {
        // 로그 전송에 성공하였습니다.
    }

    @Override
    public void onFiltered(LogObject log, LogFilter filter) {
        // 로그 필터에 의해 로그가 필터링되었습니다.
    }

    @Override
    public void onSaved(LogObject log) {
        // 네트워크 차단으로 로그가 저장되었습니다.
    }

    @Override
    public void onError(LogObject log, int errorCode, String errorMessage) {
        // 전송에 실패하였습니다.
    }
});
```

## 크래시 SDK 사용하기

* [TOAST Crash Reporter > Android](./crash-reporter-android) 사용 가이드

이 체험은 다음과 같이 설명될 수 있습니다.

```
This auth starter implements withAuthenticator HOC to provide a basic authentication flow for signing up signing in users as well as protected client side routing using AWS Amplify.

Auth features: User sign up, User sign in, Multi-factor Authentication, User sign-out.
```

여기서 키워드는 'Auth features: User sign up, User sign in, Multi-factor Authentication, User sign-out.'인데, 보호된(protected) 클라이언트 사이드 라우팅과 사용자 로그인에 대한 기본적인 인증 흐름을 제공하는 기본 스타터 팩이라고 생각하시면 됩니다.

이를 위해 가장 먼저 진행할 예제는 다음과 같습니다(내용에 대한 출처는 [여기](https://github.com/aws-samples/create-react-app-auth-amplify)를 참고하시기 바랍니다).

> 만약 세미나가 진행되고 있다면, 앞에서 발표하는 진행자와 함께 다음을 진행하시면 됩니다!

[View Demo](https://master.d2ka7y7551sk8n.amplifyapp.com/)

![Amplify Auth](https://github.com/aws-samples/create-react-app-auth-amplify/raw/master/src/images/auth.gif)

## Deploy with the AWS Amplify Console

The AWS Amplify Console provides hosting for fullstack serverless web apps. [Learn more](https://console.amplify.aws). Deploy this app to your AWS account with a single click:

[![amplifybutton](https://oneclick.amplifyapp.com/button.svg)](https://console.aws.amazon.com/amplify/home#/deploy?repo=https://github.com/aws-samples/create-react-app-auth-amplify)

The Amplify Console will fork this repo in your GitHub account, and then build and deploy your backend and frontend in a single workflow. Your app will be available at `https://master.appid.amplifyapp.com`.

## Run locally with the Amplify CLI

1. Clone the repo that was just forked in your account

  ```
  git clone git@github.com:<username>/create-react-app-auth-amplify.git

  cd create-react-app-auth-amplify && npm install
  ```

2. Import the backend environment deployed by the Amplify Console to your repo (the `amplify/team-provider.json` file contains information on all backend environments in your AWS account). The GIF below shows how you to copy the `amplify env import` command from the Amplify Console. 

<img src="https://github.com/aws-samples/create-react-app-auth-amplify/blob/master/src/images/import-backend.gif" width="800"/>

3. Paste this command into your terminal at the root of your repo. You should see the `amplify/team-provider.json` updated with a backend named `amplify`.

  ```
  amplify env import --name amplify --config "{<stack>}" --awsInfo "{<profile>}" --yes

  Successfully added environment from your project
  ```

3. Initialize the Amplify CLI with the `amplify` environment.

  ```
  amplify init
  ? Do you want to use an existing environment? Yes
  ? Choose the environment you would like to use: (Use arrow keys)
  > amplify
  ```

4. Run locally

  ```
  npm start
  ```

Checkout Nader Dabit's [Complete Guide to User Authentication](https://dev.to/dabit3/the-complete-guide-to-user-authentication-with-the-amplify-framework-2inh).

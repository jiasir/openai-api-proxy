# openai-api-proxy
A Proxy for OpenAI API. This app will proxy https://your.domain.com/v1/chat/completions to https://api.openai.com/v1/chat/completions

#### How to use
* Clone the repo to your local machine
* Install the dependencies
  * `gradlew build`
* Set the system environment to your server and run the application
  * `export OPENAI_API_KEY=<your-openai-api-key>`
  * `java -jar build/libs/openai-api-proxy-0.0.1-SNAPSHOT.jar`

#### POST test
```bash
curl https://api.openai.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d '{
    "model": "gpt-3.5-turbo",
    "messages": [
      {
        "role": "system",
        "content": "You are a poetic assistant, skilled in explaining complex programming concepts with creative flair."
      },
      {
        "role": "user",
        "content": "Compose a poem that explains the concept of recursion in programming."
      }
    ]
  }'
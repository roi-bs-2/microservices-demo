# Self Service Actions

Drive developer productivity by allowing developers to use self-service actions like scaffolding a service or provisioning a cloud resource. [Read more](https://docs.getport.io/actions-and-automations/create-self-service-experiences/)

Port's action model is designed to be flexible and can be used to cover a wide range of use-cases:

1. **Unopinionated** - flexible UI to create a wide range of self-service actions.
2. **Leverages existing infrastructure and automations** as the backend of your actions.
3. **Loosely coupled** to your infrastructure and architecture.
4. **Stateful** - every invoked action affects the software catalog by adding/modifying/deleting one or more entities.
5. **Secure by design** - does not require keys to sensitive infrastructure by using an event-based model. All actions are audited and can include guardrails like manual approval and TTL.

# Example - Call an external API

In this example, we'll create a self-service action that calls an external API from a GitHub Actions workflow.

## Prerequisites

Make sure you accomplished the [Getting Started](./GETTING-STARTED.md) guide.

## Create a self-service action

1. Go to the [Actions](https://app.getport.io/self-serve) page.
2. Click on the `+ Action` button.
3. Fill the Title, Description, and Icon as you see fit.
4. Make sure `Operation` is set to `Create` & Hit `Next`.
5. Configure the user input fields by clicking on the `+ Input` button.
   - add `Webhook URL` - Type `Text`
   - add `Payload` - Type `Text`
6. Hit `Next`.
7. Select the **Run Github workflow** backend.
   - Fill in `Organization` - The organization name you forked this repository into.
   - Fill in `Repository` - Probably `microservices-demo`, the repository name you forked this repository into.
   - Fill in `Worflow file name` - In this case `setup-dummy-s3-bucket.yml`, the workflow file name you want to run.
8. Hit `Next`.
9. Hit `Create`.

Congratulations! You should see the action in the UI.

## Test the action

1. Go to the [Actions](https://app.getport.io/self-serve) page.
2. Find the action you just created, and click `Create`.
3. Fill in the `Webhook URL` and `Payload` fields.
   - You can use [webhook.site](https://webhook.site/) to receive the webhook for testing.
4. Hit `Create`.

# Further reading

- [Self-Service Actions](https://docs.getport.io/actions-and-automations/create-self-service-experiences/)
- [Supported Backends for Self-Service Actions](https://docs.getport.io/actions-and-automations/setup-backend/)

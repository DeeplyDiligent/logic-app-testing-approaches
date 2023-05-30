

From a requirements perspective we are hoping to achieve the ability to run “Unit Tests” against our logic apps to enable quick execution on local developer machines and within DevOps Pipelines. To achieve this I think there needs to be some kind of mocking of dependencies (Triggers, ServiceBus, External Connections, APIs etc). Alternatively we would also be happy with automating the execution of logic app workflows after they have been deployed to a UAT / TESTING environment, this is more of an integration test but still very useful.

Reviewing the options below:


| OPTION | Name / Links | Owner / Creator | Pros / Cons |
| ------ | ------------ | --------------- | ----------- |
| (1) | [Logic App Sample Test Framework](https://techcommunity.microsoft.com/t5/integrations-on-azure-blog/automated-testing-with-logic-apps-standard/ba-p/2960623) <br> Code: [GitHub](https://github.com/Azure/logicapps/tree/master/LogicAppsSampleTestFramework) | Microsoft | Pros:<br>- Microsoft owned<br>Cons:<br>- Limited support for triggers other than HTTP<br>- Is it being maintained, not much activity?<br>- Tests require logic app to be deployed<br>- No mocking |
| (2) | [Microsoft – Testing workflows with mock data in Azure Logic Apps (Preview)](https://learn.microsoft.com/en-us/azure/logic-apps/test-logic-apps-mock-data-static-results?tabs=standard) | Microsoft | Pros:<br>- Good start<br>Cons:<br>- Limited activity support (http only so far) |
| (3) | [Michael Stephensen (integration-playbook.io)](https://www.integration-playbook.io/docs/logic-app-test-manager-1) <br> Code: [GitHub](https://github.com/michaelstephensonuk/IntegrationPlaybook-LogicApp-Standard-Testing) | Michael Stephensen | Pros:<br>- Good approach for targeting Integration Testing requiring workflows to be deployed<br>Cons:<br>- Not Microsoft<br>- No Mocking, therefore no "Unit Testing"<br>- Targets Integration testing only |
| (4) | [LogicApp Unit Testing](https://github.com/LogicAppUnit/TestingFramework/wiki) <br> Code: [GitHub](https://github.com/LogicAppUnit/TestingFramework) | Mark Abrams | Pros:<br>- Seems to align with what we are trying to achieve: Unit Testing, Mocking, Pipelines<br>- Recent git activity<br>Cons:<br>- Not Microsoft |

Other Resources:

* https://learn.microsoft.com/en-us/azure/logic-apps/test-logic-apps-mock-data-static-results?tabs=standard
* https://www.youtube.com/watch?v=5obPpZ7tAEU&ab_channel=KentWeare
* https://www.youtube.com/watch?v=NoYDN3P89AE&ab_channel=MikeStephenson
* https://www.integration-playbook.io/v1/docs/generate-an-automate-test
* https://stackoverflow.com/questions/48065968/how-do-i-write-unit-test-for-logic-apps-steps-using-ms-unit-project-c-sharp-code

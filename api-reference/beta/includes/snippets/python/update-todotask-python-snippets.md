---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = TodoTask(
	due_date_time = DateTimeTimeZone(
		date_time = "2020-07-25T16:00:00",
		time_zone = "Eastern Standard Time",
	),
)

result = await graph_client.me.todo.lists.by_todo_task_list_id('todoTaskList-id').tasks.by_todo_task_id('todoTask-id').patch(request_body)


```
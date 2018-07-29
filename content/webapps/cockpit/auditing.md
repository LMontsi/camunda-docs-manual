---

title: 'Auditing of Cockpit Operations'
weight: 45

menu:
  main:
    identifier: "user-guide-cockpit-operations"
    parent: "user-guide-cockpit"
    name: "Auditing"
    pre: "Audit operations performed in Cockpit"

---


Since Cockpit is a very powerful tool, it is often desired to inspect which user performed which operation for auditing purposes. Cockpit operations that change state are logged in the BPM platform's [user operation log]({{< ref "/user-guide/process-engine/history.md#user-operation-log" >}}) that is part of the process engine history. The log allows to understand

* which user performed an operation
* which operation was performed
* when the operation was performed
* which entities (process instances, tasks, etc.) were involved
* which changes were made

To get a more detailed explanation about the Java and REST API methods to get user operations, check out [this url]({{< ref "/user-guide/process-engine/history.md#accessing-the-user-operation-log" >}}).


# User Operation Log in Cockpit
{{< img src="../img/cockpit-user-operation-log.png" title="Batch View Page" >}}

Cockpit provides the possiblity to view the activity of different users in the User Operations table. The table can be found in both the process definition and instance history views.
The table is a representation of the history of various user operations and information about the property changes involved.
Rows are grouped by operation to provide clear insights on the changes produced by each operation.

# Cockpit Operation Log Entries

The following table serves as an index that relates operations in the Cockpit user interface to operations in the user operation log. Whenever a listed operation is performed in Cockpit, entries for the corresponding user operations are created in the user operation log. The following list relates UI operations to the operation and entity types in the operation log. See the [user operation log documentation]({{< ref "/user-guide/process-engine/history.md#glossary-of-operations-logged-in-the-user-operation-log" >}}) for details on these types.

<table class="table table-striped">
  <tr>
    <th>UI Operation</th>
    <th>Operation Type</th>
    <th>Entity Type</th>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/suspension.md#process-definition-suspension" >}}">Activate a Process Definition</a></td>
    <td>ActivateProcessDefinition</td>
    <td>ProcessDefinition</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/suspension.md#process-definition-suspension" >}}">Suspend a Process Definition</a></td>
    <td>SuspendProcessDefinition</td>
    <td>ProcessDefinition</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/suspension.md#process-instance-suspension" >}}">Activate a Process Instance</a></td>
    <td>Activate</td>
    <td>ProcessInstance</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/suspension.md#process-instance-suspension" >}}">Suspend a Process Instance</a></td>
    <td>Suspend</td>
    <td>ProcessInstance</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/suspension.md#job-definition-suspension" >}}">Activate a Job Definition</a></td>
    <td>ActivateJobDefinition</td>
    <td>JobDefinition</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/suspension.md#job-definition-suspension" >}}">Suspend a Job Definition</a></td>
    <td>SuspendJobDefinition</td>
    <td>JobDefinition</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/process-instance-view.md#cancel-a-process-instance" >}}">Cancel a Process Instance</a></td>
    <td>Delete</td>
    <td>ProcessInstance</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/process-definition-view.md#cancel-multiple-process-instances" >}}">Cancel Multiple Process Instances</a></td>
    <td>Delete</td>
    <td>ProcessInstance</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/process-instance-view.md#adding-variables" >}}">Add Process Instance Variables</a></td>
    <td>SetVariable</td>
    <td>Variable</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/process-instance-view.md#editing-variables" >}}">Edit Process Instance Variables</a></td>
    <td>ModifyVariable</td>
    <td>Variable</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/failed-jobs.md#retry-a-failed-job" >}}">Retry a Failed Job</a></td>
    <td>SetJobRetries</td>
    <td>Job</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/failed-jobs.md#batch-retry" >}}">Batch Retry of Failed Jobs</a></td>
    <td>SetJobRetries</td>
    <td>Job</td>
  </tr>
  <tr>
    <td><a href="{{< ref "/webapps/cockpit/bpmn/process-instance-modification.md" >}}">Process Instance Modification</a></td>
    <td>ModifyProcessInstance</td>
    <td>ProcessInstance</td>
  </tr>
  <tr>
    <td>Set Task Assignee</td>
    <td>Assign</td>
    <td>Task</td>
  </tr>
  <tr>
    <td>Add Task Candidate Group</td>
    <td>AddGroupLink</td>
    <td>IdentityLink</td>
  </tr>
  <tr>
    <td>Remove Task Candidate Group</td>
    <td>DeleteGroupLink</td>
    <td>IdentityLink</td>
  </tr>
</table>

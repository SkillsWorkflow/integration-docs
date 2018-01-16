# SAP

On premises agent to send Jobs and Projects to SAP from Skills Workflow

<h3>Framework/Tools/Dependencies</h3>
<ul>
<li>.NET Framework 4.6.2</li>
</ul>

<h3>Running Instructions - Windows</h3>
<ol>
<li>Open <strong>app.config</strong> file and change the app settings accordingly. These settings are explained further below.</li>
<li>Run the application</li>
</ol>

<h3>Scheduling Instructions - Windows</h3>
<ol>
<li>SkillsWorkflow.SAP application should be run as a Scheduled Task. Create a new Scheduled Task in Task Scheduler.</li>
<li>Manage the created Task. Choose a user with permissions to run the task and set a trigger to run the task in repeat mode.</li>
<li>The SkillsWorkflow.SAP task should run with a recurring short period of time.</li>
<li>Set the task to run the SkillsWorkflow.SAP.exe file. No entry parameters are required</li>
</ol>

<h3>SkillsWorkflow.SAP Settings</h3>
<ol>
<li><strong>SkillsWorkflow</strong>
<ul>
<li><strong>ApiUrl</strong> - SkillsWorkflow Api base url. It depends on the Environment and Tenant being used. It has the following scructure https://api-tenant-environment-we.skillsworkflow.com. Use the name of the company provided to you for the parameter "tenant". For "environment" use "prod", "test" or "dev" for one of Skills Workflow's Environments: Production, Testing, Development.</li>
<li><strong>AppId</strong> - SkillsWorkflow Tenant application id. This id must be requested to SkillsWorkflow team. It will be used to ensure comunication with SkillsWorkflow api.</li>
<li><strong>AppSecret</strong> - SkillsWorkflow Tenant application secret. It is used with Tenant application id.</li>
</ul>
</li>
<li><strong>SAP</strong>
<ul>
<li><strong>si_ws2prx_masterjob_skillsBinding</strong> - Jobs transfer binding configuration to connect to the SAP endpoint.</li>
<li><strong>si_ws2prx_status_skillsBinding</strong> - Status update binding configuration to connect to the SAP endpoint. </li>
</ul>
</li>
</ol>

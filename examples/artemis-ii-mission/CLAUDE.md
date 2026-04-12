# eeoc-process-models

Included here are BPMN files that follow the BPMN XML Standard.  These BPMN files refernce DMN files, a 
companion standard.  

## About SpiffWorkflow

These BPMN files have some spiffworkflow extension elements within them.  SpiffWorkflow is a BPMN 
Execution Engine.  It is able to execute these bpmn files.  SpiffWorkflow relies exclusively on Python 
and Json Schemas to make the processes executable.

Script tasks contain python scripts.  Most tasks can also have pre-scripts and post-scripts that are also
python scripts.  These scripts are executed using the RestrictedPython library and are limited to subset 
of available global functions in python, which are enumerated in this fucntion: https://github.com/sartography/spiff-arena/blob/93134de5ea342eb0f8b9f2b0cf1f42c180e1de51/spiffworkflow-backend/src/spiffworkflow_backend/services/process_instance_processor.py#L290

Many tasks contain an Instructions element.  This contains markdown with Jinja2 syntax to inject variables 
into the markdown.

User tasks reference Json files located in the same directory that conform to the json-schema specification, 
and an optional ui schema designed to work the RJSF form rendering library. The naming convention is [unique name]-schema.json
for the json schema, there may also be a matching [unique-name]-uischema.json that contains RJSF specific rendering instructions
and a [unique-name]-exampledata.json to use for populating the form when it is rendered in tests so you can see the form completed.

Service tasks make API calls to external systems, and expect json to be returned, which is then written
into a local variable.

Any data collected in one task is copied and passed on to the next task. 

Timer Events with a duration must specify the duration in ISO 8601 durations format.
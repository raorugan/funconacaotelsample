**OTEL for Azure Functions on Azure Container Apps**

This sample shows you how to configure your function app to export log and trace data in an OpenTelemetry format. 
Azure Functions generates telemetry data on your function executions from both the Functions host process and the language-specific worker process in which your function code runs. 
By default, this telemetry data is sent to Application Insights using the Application Insights SDK. However, you can choose to export this data using OpenTelemetry semantics. While you can still use an OpenTelemetry format
to send your data to Application Insights, you can now also export the same data to any other OpenTelemetry-compliant endpoint.

To deploy on Azure container apps you may refer to function images here - [Azure Functions Image Artifact Registry](https://mcr.microsoft.com/en-us/artifact/mar/azure-functions/dotnet/about)

You can obtain these benefits by enabling OpenTelemetry in your function app:

Correlation across traces and logs being generated both at the host and in your application code.
Consistent, standards-based generation of exportable telemetry data.
Integrates with other providers that can consume OpenTelemetry-compliant data.
OpenTelemetry is enabled at the function app level, both in host configuration (host.json) and in your code project. Functions also provides a client optimized experience for exporting OpenTelemetry data from your function code that's running in a language-specific worker process.

**Considerations for OpenTelemetry**
When you export your data using OpenTelemetry, keep these current considerations in mind.

When the host is configured to use OpenTelemetry, only logs and traces are exported. Host metrics aren't currently exported.

You can't currently run your app project locally using Core Tools when you have OpenTelemetry enabled in the host. You currently need to deploy your code to Azure to validate your OpenTelemetry-related updates.

At this time, only HTTP trigger and Azure SDK-based triggers are supported with OpenTelemetry outputs.

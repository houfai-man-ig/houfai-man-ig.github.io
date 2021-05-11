
## Rules of Engagement
You will find a project in Github that we use to generate our “rules of engagement”: [ig-orchestrations](https://github.com/IG-Group/ig-orchestrations)

The project generates API Documents, JSON Schema, Java bindings and defines TypeScript interfaces. 

You don’t need to build this project as the artifacts are published to “oss.sonatype.org” and can be downloaded from there.
You’ll want to download the roe.zip for the WebSocket API.

See: [oss.sonatype.org](https://oss.sonatype.org/#nexus-search;quick~com.ig) 


## WebSocket APIs
The WebSocket APIs are built on FIX/P and FIX Orchestra. The latter is a new FIX Trading Community initiative that is in active development.
Ref: 
-	[Fix Trading](https://www.fixtrading.org/)
-	[Fix Orchestra](https://www.fixtrading.org/standards/fix-orchestra/)
-	[Fix Trading Standards](https://www.fixtrading.org/standards/)

We’re actively working on improving this project so do expect to see some changes.

The project structure is as follows:

```
│   readme.md - Describes how to build the project using Apache Maven and NPM, the outputs of the mvn build steps is generally in subdirectories named  “target”.
└───chart-data - For the Chart Data API this contains the JSON Schema source code and build for the Java bindings.
│   └───java-bindings - Generates the Java/JSON bindings.
│   └───json-schema - Source code for the JSON schema.
└───fixp - For the FIX Performance protocol this contains the JSON Schema source code and build for the Java bindings.
│   └───java-binding - Generates the Java/JSON bindings
│   └───json-schema - Source code for the JSON schema.
└───ig-us-rfed – Contains the FIX “orchestration” and supporting information for the IG US RFED API.
│   |───document/ 
│   |   └───document-websocket - Generates the Rules of Engagement in markdown and HTML for the WebSocket API.
│   |   └───document-fixt - Generates the Rules of Engagement in markdown and HTML for the FIX50sp2/FIXT1.1 API.
│   └───document-generation – Generates simple HTML documents using a FIX Trading Community utility - see note below.
│   └───java-binding - Generates the Java/JSON bindings.
│   └───json-schema – Generates the JSON Schema.
│   └───orchestration – Generates the IG RFED “orchestration” from the FIX Standard orchestration – an XML document.
│   └───ts-interface - TypeScript interfaces.
```

## Examples
You can also find simple WebSocket Client Examples here:
- [Node Client](https://github.com/IG-Group/fix-ws-client-example)
- [Python Pre-Trade](https://github.com/IG-Group/ig-us-websocket-client-python-example) 
- [Python Trade](https://github.com/IG-Group/ig-us-websocket-trade-python-example)
- [Java](https://github.com/IG-Group/ig-us-websocket-java-examples)

FYI - Logging onto the WebSocket API using username and password results in a “logout” messages being sent to web platform (as it does when you try to log on to the web platform multiple times). 

For testing you can log onto the API first. Logging onto web platform does not log out the API.
These are the Demo environment Hosts, port and URLs.  See the example.

| **API**   | **Host**                 | **Port** | **Path**  |
|-----------|--------------------------|----------|-----------|
| Pre Trade | demo-iguspretrade.ig.com | 443	    | /pretrade |
| Trade	    | demo-igustrade.ig.com	   | 443	    | /trade    |

> Example:	wss://iguspretrade.ig.com/pretrade	 	 

## Contact

For queries regarding integration, please contact Kevin Downey.

| **Name**      | **Contact Email**    |
|---------------|----------------------|
| Kevin Downey  | Kevin.Downey@ig.com  |

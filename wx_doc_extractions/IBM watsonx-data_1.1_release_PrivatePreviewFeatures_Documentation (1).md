IBM watsonx.data v1.1.0

Private Preview 2023-11-29

## Notices

This information was developed for products and services offered in the US. This material might be available from IBM in other languages. However, you may be required to own a copy of the product or product version in that language in order to access it.

IBM may not offer the products, services, or features discussed in this document in other countries. Consult your local IBM representative for information on the products and services currently available in your area. Any reference to an IBM product, program, or service is not intended to state or imply that only that IBM product, program, or service may be used. Any functionally equivalent product, program, or service that does not infringe any IBM intellectual property right may be used instead. However, it is the user's responsibility to evaluate and verify the operation of any non-IBM product, program, or service.

IBM may have patents or pending patent applications covering subject matter described in this document. The furnishing of this document does not grant you any license to these patents. You can send license inquiries, in writing, to:

IBM Director of Licensing IBM Corporation North Castle Drive, MD-NC119 Armonk, NY 10504-1785 US

For license inquiries regarding double-byte character set (DBCS) information, contact the IBM Intellectual Property Department in your country or send inquiries, in writing, to:

Intellectual Property Licensing Legal and Intellectual Property Law IBM Japan Ltd. 19-21, Nihonbashi-Hakozakicho, Chuo-ku Tokyo 103-8510, Japan

INTERNATIONAL BUSINESS MACHINES CORPORATION PROVIDES THIS PUBLICATION "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF NON-INFRINGEMENT, MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE. Some jurisdictions do not allow disclaimer of express or implied warranties in certain transactions, therefore, this statement may not apply to you.

This information could include technical inaccuracies or typographical errors. Changes are periodically made to the information herein; these changes will be incorporated in new editions of the publication. IBM may make improvements and/or changes in the product(s) and/or the program(s) described in this publication at any time without notice.

Any references in this information to non-IBM websites are provided for convenience only and do not in any manner serve as an endorsement of those websites. The materials at those websites are not part of the materials for this IBM product and use of those websites is at your own risk.

IBM may use or distribute any of the information you provide in any way it believes appropriate without incurring any obligation to you.

Licensees of this program who wish to have information about it for the purpose of enabling: (i) the exchange of information between independently created programs and other programs (including this one) and (ii) the mutual use of the information which has been exchanged, should contact:

IBM Director of Licensing IBM Corporation North Castle Drive, MD-NC119 Armonk, NY 10504-1785 US Such information may be available, subject to appropriate terms and conditions, including in some cases, payment of a fee.

The licensed program described in this document and all licensed material available for it are provided by IBM under terms of the IBM Customer Agreement, IBM International Program License Agreement or any equivalent agreement between us.

The performance data and client examples cited are presented for illustrative purposes only. Actual performance results may vary depending on specific configurations and operating conditions.

Information concerning non-IBM products was obtained from the suppliers of those products, their published announcements or other publicly available sources. IBM has not tested those products and cannot confirm the accuracy of performance, compatibility or any other claims related to non-IBM products. Questions on the capabilities of non-IBM products should be addressed to the suppliers of those products.

This information contains examples of data and reports used in daily business operations. To illustrate them as completely as possible, the examples include the names of individuals, companies, brands, and products. All of these names are fictitious and any similarity to actual people or business enterprises is entirely coincidental.

## COPYRIGHT LICENSE:

This information contains sample application programs in source language, which illustrate programming techniques on various operating platforms. You may copy, modify, and distribute these sample programs in any form without payment to IBM, for the purposes of developing, using, marketing or distributing application programs conforming to the application programming interface for the operating platform for which the sample programs are written. These examples have not been thoroughly tested under all conditions. IBM, therefore, cannot guarantee or imply reliability, serviceability, or function of these programs. The sample programs are provided "AS IS", without warranty of any kind. IBM shall not be liable for any damages arising out of your use of the sample programs.

Each copy or any portion of these sample programs or any derivative work must include a copyright notice as follows:

©

(your company name) (year).

Portions of this code are derived from IBM Corp. Sample Programs.

©

Copyright IBM Corp. _enter the year or years_.

## Trademarks

IBM, the IBM logo, and ibm.com are trademarks or registered trademarks of International Business Machines Corp., registered in many jurisdictions worldwide. Other product and service names might be trademarks of IBM or other companies. A current list of IBM trademarks is available on the web at "Copyright and trademark information" at www.ibm.com/legal/copytrade.shtml.

Linux is a registered trademark of Linus Torvalds in the United States, other countries, or both.

Microsoft, Windows, Windows NT, and the Windows logo are trademarks of Microsoft Corporation in the United States, other countries, or both.

UNIX is a registered trademark of The Open Group in the United States and other countries.

Java and all Java-based trademarks and logos are trademarks or registered trademarks of Oracle and/or its affiliates.

## Terms and conditions for product documentation

Permissions for the use of these publications are granted subject to the following terms and conditions.

## Applicability

These terms and conditions are in addition to any terms of use for the IBM website.

## Personal use

You may reproduce these publications for your personal, noncommercial use provided that all proprietary notices are preserved. You may not distribute, display or make derivative work of these publications, or any portion thereof, without the express consent of IBM.

## Commercial use

You may reproduce, distribute and display these publications solely within your enterprise provided that all proprietary notices are preserved. You may not make derivative works of these publications, or reproduce, distribute or display these publications or any portion thereof outside your enterprise, without the express consent of IBM.

## Rights

Except as expressly granted in this permission, no other permissions, licenses or rights are granted, either express or implied, to the publications or any information, data, software or other intellectual property contained therein.

IBM reserves the right to withdraw the permissions granted herein whenever, in its discretion, the use of the publications is detrimental to its interest or, as determined by IBM, the above instructions are not being properly followed.

You may not download, export or re-export this information except in full compliance with all applicable laws and regulations, including all United States export laws and regulations.

IBM MAKES NO GUARANTEE ABOUT THE CONTENT OF THESE PUBLICATIONS. THE PUBLICATIONS ARE PROVIDED "AS-IS" AND WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO IMPLIED WARRANTIES OF MERCHANTABILITY, NON-INFRINGEMENT, AND FITNESS FOR A PARTICULAR PURPOSE.

## Contents

| Notices...................................................................................................................i |
| --- |
| Trademarks...................................................................................................................................................ii |
| Terms and conditions for product documentation...................................................................................... ii |
| Chapter 1. Private preview ....................................................................................1 |
| Limitations and known issues......................................................................................................................1 |
| Prestissimo ..................................................................................................................................................2 Provisioning a Prestissimo engine..........................................................................................................2 |
| Running SQL queries on Prestissimo..................................................................................................... 2 |
| Customizing Prestissimo for watsonx.data................................................................................................. 3 |
| Milvus ...........................................................................................................................................................4 |
| Adding a service - Milvus........................................................................................................................4 |
| Connecting to Milvus service..................................................................................................................4 |
| Using self-signed certificates for Milvus................................................................................................7 |
| OptimizerPlus .............................................................................................................................................. 8 |
| About OptimizerPlus...............................................................................................................................8 |
| Installing OptimizerPlus......................................................................................................................... 9 |
| Syncing OptimizerPlus with watsonx.data metastore.........................................................................11 |
| Running Presto queries and inspecting logs .......................................................................................13 |

Index.................................................................................................................. 15

## Chapter 1. Private preview

Some features are available in IBM® watsonx.data Version 1.1.0 as private preview only.

Important: You can use the private preview features only for internal use for evaluation purposes and not for use in a production environment.

## Limitations and known issues

The following limitations and known issues apply to IBM watsonx.data.

* Prestissimo fails to query an external partitioned table

* Limitations - Prestissimo

* Limitations - Milvus

## Prestissimo fails to query an external partitioned table

## Applies to: 1.1.0 and later

When you query an external table with CHAR data type columns, the query fails to run. This issue occurs due to the limitation that Prestissimo does not support CHAR data types.

Workaround: Change the CHAR data type column to VARCHAR data type.

## Limitations - Presstissimo

Applies to: 1.1.0 and later

* File formats such as Parquet and DWRF are supported.

* Only a Hive connector is supported.

* TPC-H/TPC-DS queries are supported.

* The following SQL statements are supported:

* – SELECT all clauses

* – CTAS statements

* DELETE FROM and CALL SQL statements are not supported.

* START, COMMIT, and ROLLBACK transactions are not supported.

* Data types CHAR, TIME, and TIME WITH TIMEZONE are not supported. These data types are subsumed by VARCHAR, TIMESTAMP, and TIMESTAMP WITH TIMEZONE.

* – IPADDRESS, IPPREFIX, UUID, kHYPERLOGLOG, P4HYPERLOGLOG, QDIGEST, and TDIGEST are not supported.

* – VARCHAR supports only a limited length. Varchar(n) with a maximum length bound is not supported.

* – TIME and TIME WITH TIMEZONE is supported in community development.

* – TIMESTAMP columns in Parquet files cannot be read

* Scalar functions:

* – IPFunctions, QDigest, HyperLogLog, and Geospatial internationalization are not supported.

* Aggregate functions:

* – QDigest, Classification metrics, and Differential entropy are not supported

* S3 and S3 compatible file systems (both read and write) are supported

## Limitation - Milvus

Applies to: 1.1.0 and later Users can create only one instance of Milvus service for a single instance of watsonx.data in IBM Cloud.

## Prestissimo

## Provisioning a Prestissimo engine

You can provision a Prestissimo engine in IBM watsonx.data to run SQL queries on your data source and fetch the queried data.

## Procedure

1. Log in to the watsonx.data console.

* 2. From the navigation menu, select Infrastructure Manager.

* 3. To provision an engine, click Add component and select Add engine.

4. In the Add engine window, provide the following details to sign up new compute to work with your

data:

| Field |Description |
| --- | --- |
| Select the engine type (Prestissimo v0.282) from the list. |Type |
| Enter your compute engine name. |Display name |
| Select Quick for predefined engine sizes or Custom for customized engine configuration. |Configuration mode |
| Select the engine size. Custom size includes 1 coordinator node and 3 worker nodes. |Size |
| Associate the available catalogs (hive_data) with the engine if necessary. |Associated catalogs (optional) |

5. Click Provision.

## Running SQL queries on Prestissimo

You can use the Query workspace interface in IBM watsonx.data to run SQL queries on a Prestissimo engine.

## Procedure

1. Log in to the watsonx.data console.

* 2. From the navigation menu, select SQL. The Query workspace page opens.

* 3. Select the Prestissimo engine from the Engine menu.

* 4. Select the catalog, schema, table, or column in which you want to run the query.

* 5. Click the overflow menu and select the query.

* 6. Click Run on to run the query.

* 7. Select the Result set or Details tab to view the results. Click the Download icon to export the result set and details to a CSV file.

* 8. Click the Save icon to save the query. A Save worksheet confirmation dialog appears.

* 9. Enter the worksheet name, click Save.

* 10. Click Saved queries to view the saved queries.

* 11. Click Explain to view the logical or distributed plan of execution for a specified SQL query.

## Customizing Prestissimo for watsonx.data

You can set additional customizations for the Prestissimo engine other than the default ones, as part of the post-install procedure. The following specifications are optional and it can be altered to change the component level customizations.

| Property |Description |Type |System property |Restart contain ers required |
| --- | --- | --- | --- | --- |
| prestissimo_wo rker_replicas |The number of Prestissimo worker replicas to deploy for parallel query execution. Increasing the number of replicas can improve query performance by distributing workloads across multiple instances. |Integer |replicas |Y |
| prestissimo_wo rker_resources _limits_cpu |The CPU resource limits for each Prestissimo worker replica. This value determines the maximum CPU usage allowed for each worker. |Integer |resources_limi ts_cpu |Y |
| rker_resources _limits_memory |prestissimo_wo The memory resource limits for each Prestissimo worker replica. This value sets the maximum memory allocation for each worker. This also impacts the config.properties.system memory-gb, config.properties.query memory-gb and config.properties.query.max memory-per-node system properties. • query-memory-gb: Specifies the |Integer |resources_limi ts_memory |Y |
|   |total memory capacity that can be used by query execution in GB. The query memory capacity should be configured less than the system memory capacity (system-memory gb) to reserve the memory for system usage such as disk spilling and cache prefetch, which are not counted in query memory usage. • system-memory-gb: It is total memory capacity used for the system. |  |  |  |
| prestissimo_wo rker_resources _requests_cpu |• query.max-memory-per-node: It is similar to query-memory-gb, but query-memory-gb is enforced by memory arbitrator. The CPU resource requests for each Prestissimo worker replica. This value specifies the desired amount of CPU |Integer |resources_requ ests_cpu |Y |
| Table 1. watsonx.data component: Prestissimo (continued) |||||
| Property |Description |Type |System property |Restart contain ers required |
| prestissimo_wo rker_resources _requests_memo ry |The memory resource requests for each Prestissimo worker replica. This value specifies the desired amount of memory for each worker. |Integer |resources_requ ests_memory |Y |
| prestissimo_wo rker_memory |The amount of memory allocated to each Prestissimo worker replica. This memory is used for query processing and other operations. (The base unit of prestissimo_worker_memory is GB.) |Integer |memory |Y |

## Milvus

## Adding a service - Milvus

Milvus is a vector database that stores, indexes, and manages massive embedding vectors that are developed by deep neural networks and other machine learning (ML) models. It is developed to empower embedding similarity search and AI applications. Milvus makes unstructured data search more accessible and consistent across various environments.

## About this task

You can add Milvus as a service in IBM watsonx.data through web console by using the following steps.

## Procedure

1. Log in to watsonx.data console.

* 2. From the navigation menu, select Infrastructure Manager.

3. To define and connect to a service, click Add component and select Add service.

4. In the Add service window, select Milvus from the Type drop-down list.

Note: Milvus is the only supported service now.

Note: Milvus SaaS is available only in IBM Cloud and not in AWS Cloud.

| Field |Description |
| --- | --- |
| Display name |Enter the service name to be displayed on the screen. |
| Storage strategy |Default. |

5. Click Provision.

## Connecting to Milvus service

You can connect to Milvus service from a client program by using CLI after provisioning Milvus as a service in IBM watsonx.data through the web console.

## Before you begin

To connect to the Milvus Server from a client program make sure that the following items are installed or available:

* Python

* pymilvus Python package. Java, GO, and Node.js can also be used. See Connect to Milvus.

* grpcurl

* curl

* Hostname and port for the Milvus server or workstation where the watsonx.data instance is installed.

* Certificates served by the Milvus server to establish the trust, see Using self-signed certificates for Milvus.

* Authorized user credentials to access the Milvus server.

* Milvus server name.

* Secure flag set to True in the Milvus server.

## About this task

Connect to a Milvus service by using the following steps:

## Procedure

* 1. Provision a Milvus service in watsonx.data through the web console. See “Adding a service - Milvus” on page 4.

* 2. Run the following command to get the Milvus service instance name:

oc get wxdengine -n ${PROJECT_CPD_INSTANCE} -o custom columns='CR-NAME:metadata.name,NAME:spec.engineDName,SERVICE:spec.engineUri' | sed 's/.zen.svc.cluster.local//

For example:

oc get wxdengine -n cpd-instance -o custom-columns='CR NAME:metadata.name,NAME:spec.engineDisplayName,SERVICE:spec.engineUri' | sed 's/.zen.svc.cluster.local//' CR-NAME NAME SERVICE lakehouse-milvus475 milvus475 ibm-lh-lakehouse-milvus475-milvus-svc.cpd instance.svc.cluster.local lakehouse-presto-01 presto-01 ibm-lh-lakehouse-presto-01-presto-svc.cpd instance.svc.cluster.local

* 3. Run the following command to get the routes of the Milvus instance by using the name obtained in the previous step.

oc get route -n ${PROJECT_CPD_INSTANCE} $ | grep NAME

For example:

oc get route -n cpd-instance | grep milvus475 ibm-lh-lakehouse-milvus475-milvus-grpc ibm-lh-lakehouse milvus475.milvus.apps.keyword.cp.fyre.ibm.com ibm-lh-lakehouse milvus475-milvus-svc 19530 passthrough None ibm-lh-lakehouse-milvus475-milvus-rest ibm-lh-lakehouse-milvus475-milvus-rest-cpd instance.apps.keyword.cp.fyre.ibm.com ibm-lh-lakehouse-milvus475-milvus-svc 9091 reencrypt None

Note: The route that is obtained with -grpc is the route for the gRPC server and the route that is obtained with -rest is the route for the REST server.

* 4. Run one of the following commands by using Python SDK (PyMilvus) or grpcurl to connect to Milvus for gRPC route:

a. Using the Python SDK (PyMilvus) command:

connections.connect(

alias='default', secure=True, server_pem_path="<path/to/grpc_certificate>", server_name="<grpc_route>", host='<grpc_route>', port='443', user='<CPD_username>',

password='<CPD_password>')

For example:

connections.connect(

alias='default',

secure=True, server_pem_path="/root/cert/milvus_grpc.crt", server_name="ibm-lh

lakehouse-milvus475.milvus.apps.keyword.cp.fyre.ibm.com",

host='ibm-lh-lakehouse-milvus475.milvus.apps.keyword.cp.fyre.ibm.com',

port='443',

user='admin',

password='v4B##..##PBY')

b. Using the grpcurl command:

i) Download the Proto files on the client machine.

ii) Run the following command to generate <base64_encoded_cred> from inside the Proto files

folder:

echo -n "<CPD_username>:<CPD_password>" | base64

For example:

[root@munch1 ~]# echo -n "<CPD_username>:<CPD_password>" | base64

PENQRF91c2VybmFtZT46PENQRF9wYXNzd29yZD4=

iii) Run the following command to connect to the Milvus server:

grpcurl -cacert /root/milvus48.crt -servername "ibm-lh-lakehouse milvus475.milvus.apps.keyword.cp.fyre.ibm.com" -H "Authorization: PENQRF91c2VybmFtZT46PENQRF9wYXNzd29yZD4=" -import-path /root/ -proto milvus.proto -d '{ "db_name": "default"}' ibm-lh-lakehouse milvus475.milvus.apps.keyword.cp.fyre.ibm.com:443 milvus.proto.milvus.MilvusService/ ShowCollections

The value for Authorization is obtained in the previous step and -import-path is the path in which Proto files are installed.

For example:

[root@munch1 ~]# echo -n "<CPD_username>:<CPD_password>" | base64 PENQRF91c2VybmFtZT46PENQRF9wYXNzd29yZD4= grpcurl -cacert /root/milvus48.crt -servername "ibm-lh-lakehouse milvus475.milvus.apps.keyword.cp.fyre.ibm.com" -H "Authorization: PENQRF91c2VybmFtZT46PENQRF9wYXNzd29yZD4=" -import-path /root/ -proto milvus.proto -d '{ "db_name": "default"}' ibm-lh-lakehouse milvus475.milvus.apps.keyword.cp.fyre.ibm.com:443 milvus.proto.milvus.MilvusService/ ShowCollections

5. Run the following command by using the curl to connect to Milvus for REST route:

curl --request GET --url "https://<rest_route>:443/<rest_endpoint>" \ --header "Authorization: Bearer <CPD_username>:<CPD_password>" \ --header "accept: application/json" \ --header "content-type: application/json" \ --cacert </path/to/rest_certificate>

For example:

curl --request GET --url "https://ibm-lh-lakehouse-milvus475-milvus-rest-cpd instance.apps.keyword.cp.fyre.ibm.com:443/healthz" \ --header "Authorization: Bearer admin:v4B##...##PBY" \ --header "accept: application/json" \ --header "content-type: application/json" \ --cacert /root/milvus_rest.crt

Note: You can do the following operations after establishing a connection with a Milvus service:

* Manage databases

* Manage collections

* Manage partitions

* Manage data

* Manage indexes

* Search and Query

For more information, see Milvus Docs.

## Using self-signed certificates for Milvus

You can access external routes for Milvus from IBM watsonx.data.

Complete the following steps to access external routes:

## Procedure

1. Run the following command to get the Milvus service instance name:

oc get wxdengine -n ${PROJECT_CPD_INSTANCE} -o custom columns='CR-NAME:metadata.name,NAME:spec.engineDName,SERVICE:spec.engineUri' | sed 's/.zen.svc.cluster.local//

For example:

oc get wxdengine -n cpd-instance -o custom-columns='CR NAME:metadata.name,NAME:spec.engineDisplayName,SERVICE:spec.engineUri' | sed 's/.zen.svc.cluster.local//' CR-NAME NAME SERVICE lakehouse-milvus475 milvus475 ibm-lh-lakehouse-milvus475-milvus-svc.cpd instance.svc.cluster.local lakehouse-presto-01 presto-01 ibm-lh-lakehouse-presto-01-presto-svc.cpd instance.svc.cluster.local

* 2. Run the following command to get the routes of the Milvus instance by using the name obtained in the previous step.

oc get route -n ${PROJECT_CPD_INSTANCE} $ | grep NAME

For example:

oc get route -n cpd-instance | grep milvus475 ibm-lh-lakehouse-milvus475-milvus-grpc ibm-lh-lakehouse milvus475.milvus.apps.keyword.cp.fyre.ibm.com ibm-lh-lakehouse milvus475-milvus-svc 19530 passthrough None ibm-lh-lakehouse-milvus475-milvus-rest ibm-lh-lakehouse-milvus475-milvus-rest-cpd instance.apps.keyword.cp.fyre.ibm.com ibm-lh-lakehouse-milvus475-milvus-svc 9091 reencrypt None

The route that is obtained with -grpc is the route for the gRPC server and the route that is obtained with -rest is the route for the REST server.

3. Run the following command to obtain self-signed certificates for the routes:

echo QUIT | openssl s_client -showcerts -connect <milvus-service-host>:443 | awk '/----- BEGIN CERTIFICATE-----/ {p=1}; p; /-----END CERTIFICATE-----/ {p=0}' > milvus-grpc.cert

For example:

echo QUIT | openssl s_client -showcerts -connect bm-lh-lakehouse milvus475.milvus.apps.keyword.cp.fyre.ibm.com:443 | awk '/-----BEGIN CERTIFICATE-----/ {p=1}; p; /-----END CERTIFICATE-----/ {p=0}' > milvus-grpc.cert

## About OptimizerPlus

In the domain of database management systems, query optimizers play a pivotal role in ensuring efficient execution of database queries. OptimizerPlus, a component of IBM watsonx.data, improves the performance of queries that are processed by engines like Presto and Prestissimo. If optimization is analyzed to be feasible, the query undergoes rewriting; otherwise, the native engine optimization takes precedence.

Within watsonx.data, OptimizerPlus operates as a component, tasked with optimizing queries. It accepts a standard SQL query as input and generates an optimized SQL equivalent, which is tailored for enhanced execution by Presto or Prestissimo. In instances where optimization is not feasible, the system reverts to using the original query.

OptimizerPlus emerges as a valuable addition to the watsonx.data, empowering users to optimize their queries and achieve enhanced performance from their engines.

## Advantages of OptimizerPlus

* Enhanced Query Performance: OptimizerPlus effectively optimizes queries, leading to significant performance improvements.

* Seamless Integration: OptimizerPlus seamlessly integrates with existing watsonx.data infrastructure, ensuring a smooth adoption process.

* Flexible Optimization: OptimizerPlus operates flexibly as users can enable and disable the feature either at global or session level.

Limitation of OptimizerPlus:

* Queries that are run in SQL editor UI or API in watsonx.data cannot use OptimizerPlus.

* OptimizerPlus cannot be configured from the watsonx.data web console as the console does not use session variables.

* OptimizerPlus cannot verify whether an original query or a rewritten query was run. Verify the log to get this information.

* OptimizerPlus cannot be upgraded. To upgrade, you must uninstall and reinstall it.

* To run commands to sync the metastores and catalogs, log in to the container.

* When metastores are synced, all schemas and tables are in the uppercase. For example, "catalog.SCHEMA.TABLE".

* Queries with partial names (for example, only table name) do not work. To get the required result, use schema name along with table name.

* For optimal performance, you must define constraints like NOT NULL, Primary key, and Foreign key in wxd_optimizerplus after the tables are synced.

* OptimizerPlus do not support views.

* Decimal and float columnss in the projection list might interchange and can cause mismatch in data type.

* Three-part name queries need quotation marks around the catalog name in lowercase (“catalog”.schema.table). Query returns an error otherwise.

* Certain queries (full outer join, anti join) do not return the correct result.

* Special characters in the identifier do not work properly.

* Interval is not supported. Use date_add.

* OptimizerPlus supports only Hive tables and not Iceberg tables.

## Installing OptimizerPlus

Install OptimizerPlus in IBM watsonx.data by following the instructions.

## Before you begin

To install OptimizerPlus in watsonx.data, the following itesms are required:

* 1. Install watsonx.data. See Installing watsonx.data.

* 2. Create buckets and associate catalogs. See Adding a bucket-catalog pair.

* 3. Restart the engine.

4. Create schemas and tables under the registered catalog. See Creating schemas and Creating tables.

* 5. Run ANALYZE command for all tables:

ANALYZE catalog_name.schema_name.table_name ;

## About this task

Install the OptimizerPlus operator in watsonx.data by using the following steps:

## Procedure

* 1. Install wxd_optimizerplus operator in the instance namespace by running the following commands by using 4.8.0 cpd-cli:

cpd-cli manage apply-olm --components=wxd_optimizerplus --release=4.8.0 --cpd_operator_ns=$ {PROJECT_CPD_INST_OPERATORS} --license_acceptance=true

* 2. Update the global settings on the cluster to configure node settings for the operator:

* a. Pause machine config pool (mcp) updates for changing CRI-O pids_limit with a KubeletConfig by running the following command:

oc patch --type=merge --patch='{"spec":{"paused":true}}' machineconfigpool/master oc patch --type=merge --patch='{"spec":{"paused":true}}' machineconfigpool/worker

* b. Update haproxy timeout to 5 minutes by running the following command:

sed -i -e "/timeout client/s/ [0-9].*/ 5m/" /etc/haproxy/haproxy.cfg

sed -i -e "/timeout server/s/ [0-9].*/ 5m/" /etc/haproxy/haproxy.cfg

systemctl restart haproxy

* c. Run the following command to change CRI-O pids_limit runtime on the OpenShift® Container Platform to make sure that services are run correctly:

oc label machineconfigpool worker custom-crio=pid-limit --overwrite oc apply -f - << EOF apiVersion: machineconfiguration.openshift.io/v1 kind: KubeletConfig metadata: name: cpd-crio-kubeletconfig spec: kubeletConfig: podPidsLimit: 16384 machineConfigPoolSelector: matchLabels: custom-crio: pid-limit EOF d. Run the following command to resume mcp updates:

oc patch --type=merge --patch='{"spec":{"paused":false}}' machineconfigpool/master oc patch --type=merge --patch='{"spec":{"paused":false}}' machineconfigpool/worker

e. Run the following command to check the status of mcp:

watch "oc get mcp"

* 3. Run the following command to create a configmap to use elevated privileges in the instance namespace:

oc apply -f - <<EOF apiVersion: v1 data: DB2U_RUN_WITH_LIMITED_PRIVS: "false" kind: ConfigMap metadata: name: db2u-product-cm namespace: cpd-instance EOF

4. Patch the engine to enable the OptimizerPlus feature by using wxd_query_optimizer variable.

By default wxd_query_optimizer is set to false. To enable OptimizerPlus, set wxd_query_optimizer= true. To optimize all the queries, set enable_optimizerplus: true.

oc patch wxdengine/lakehouse-presto-01 \ --type=merge \ -n cpd-instance \ -p '{ "spec": { "wxd_query_optimizer": true, "enable_optimizerplus": true } }'

5. Restart Big SQL by running the following commands:

oc get db2uinstance

oc get pod | grep db2u

Note: Wait for 10 minutes for the instance to be ready after restarting Big SQL.

6. Run the following commands to check the status:

oc exec -it c-lakehouse-oaas-db2u-0 -n ${PROJECT_CPD_INST_OPERANDS} -- sh

bigsql stop && bigsql start bigsql status

## Additional settings

## About this task

You can verify and do the following additional settings if the variables are not updated:

* 1. Registry variable settings

* a. Run the following command to get the existing registry variable settings:

db2set

b. Update the values as follows if they are not updated:

db2set DB2_ENABLE_PRESTO_MODE=true db2set DB2_ENABLE_PRESTO_3PART_NAMES=true db2set DB2_WORKLOAD=ANALYTICS db2set DB2_REDUCED_OPTIMIZATION="EGAD 0,STARJN_CARD ON 1,NO_PEA" db2set DB2_EXTENDED_OPTIMIZATION="REDSCANELIM_UCP ON,PCD ON,EXP_GRPSETS_BYREPL ON,MRG_DISJ_SCALARSQ_CASE ON,COLJOIN 1,JFR ON"

* 2. OAAS db configuration settings

a. Update the configuration as follows if it is not updated:

db2 connect to oaas db2 get db cfg db2 update db cfg for OAAS using LARGE_AGGREGATION NO

bigsql stop bigsql start bigsql status

## Syncing OptimizerPlus with watsonx.data metastore

## About this task

Complete the following steps to sync OptimizerPlus operator with the catalog and schema metastore data in watsonx.data:

## Procedure

* 1. From the OpenShift terminal, run the following command to copy the instance key (LH_INSTANCE_SECRET):

oc extract secret/ibm-lh-config-secret -n ${PROJECT_CPD_INST_OPERANDS} --to=-

2. Configure connection settings to watsonx.data for all catalogs

oc exec -it c-lakehouse-oaas-db2u-0 -n ${PROJECT_CPD_INST_OPERANDS} -- sh

3. Run the following command to get certificates:

mkdir /mnt/external/oaas

echo QUIT | openssl s_client -showcerts -connect ibm-lh-lakehouse-hive-metastore-svc.cpd instance.svc.cluster.local:9083 | awk '/----- BEGIN CERTIFICATE-----/ {p=1}; p; /-----END CERTIFICATE-----/ {p=0}' > /mnt/external/oaas/ wxd.cert

* 4. Connect to Db2 and register an external metastore. Example shown with tpcds_1gb_aws.

su - ${DB2INSTANCE}

db2 connect to ${DBNAME}

db2

CALL SYSHADOOP.REGISTER_EXT_METASTORE('tpcds_1gb_aws','type=watsonx-data,uri=thrift://ibm lh-lakehouse-hive-metastore-svc.cpd

instance.svc.cluster.local:9083', ?, ?);

CALL SYSHADOOP.SET_EXT_METASTORE_PROPERTY('tpcds_1gb_aws', 'use.SSL', 'true', ?, ?); CALL SYSHADOOP.SET_EXT_METASTORE_PROPERTY('tpcds_1gb_aws', 'ssl.cert', '/oaas/ wxd.cert', ?, ?);

CALL SYSHADOOP.SET_EXT_METASTORE_PROPERTY('tpcds_1gb_aws', 'auth.mode', 'PLAIN', ?, ?);

5. Use the instance key LH_INSTANCE_SECRET generated in Step 1 to run the following command: CALL SYSHADOOP.SET_EXT_METASTORE_PROPERTY('tpcds_1gb_aws', 'auth.plain.credentials', 'lakehouse:_LH_INSTANCE_SECRET_', ?, ?);

6. Run the following commands to sync the OptimizerPlus with watsonx.data metastore:

CALL SYSHADOOP.EXTERNAL_CATALOG_SYNC('tpcds_1gb_aws', 'tpcds1gb_schema', '.*', 'SKIP', 'CONTINUE', 'OAAS');

Note: Repeat this step for all schemas in the catalog.

7. Run the following command to test if synced table is working:

db2 => select * from "catalog_name".schema_name.table_name

Note: 'OAAS' mode syncs only table definitions and hive stats, not any rows.

8. Repeat steps 4 to 7 for each catalog if there are more than one catalog.

* 9. Defining constraints.

a) Run the command to log in to the container.

oc exec -it c-lakehouse-oaas-db2u-0 -- sh su - ${DB2INSTANCE}

* b) Create an SQL file to define primary key, foreign key, and not null column constraints.

For example, if you have the following three tables with the given columns,

* Employees (EmployeeID, FirstName, LastName, Department, and Salary )

* Departments (DepartmentID and DepartmentName)

* EmployeeDepartmentMapping (MappingID, EmployeeID, and DepartmentI)

Run the following ALTER commands OptimizerPlus to ensure that the constrained information is propagated:

-- NOT NULL ALTER TABLE "catalog_name".schema_name.Employees ALTER COLUMN FirstName SET NOT NULL ALTER COLUMN LasttName SET NOT NULL ALTER COLUMN Salary SET NOT NULL ALTER COLUMN EmployeeID SET NOT NULL; ALTER TABLE "catalog_name".schema_name.Departments ALTER COLUMN DepartmentName SET NOT NULL ALTER COLUMN DepartmentID SET NOT NULL ; ALTER TABLE "catalog_name".schema_name.EmployeeDepartmentMapping ALTER COLUMN MappingID SET NOT NULL ; -- PRIMARY KEY ALTER TABLE "catalog_name".schema_name.Employees ADD PRIMARY KEY (EmployeeID) NOT ENFORCED; ALTER TABLE "catalog_name".schema_name.Departments ADD PRIMARY KEY (DepartmentID) NOT ENFORCED; ALTER TABLE "catalog_name".schema_name.EmployeeDepartmentMapping ADD PRIMARY KEY (MappingID) NOT ENFORCED; -- FOREIGN KEY ALTER TABLE "catalog_name".schema_name.EmployeeDepartmentMapping ADD FOREIGN KEY (EmployeeID) REFERENCES "catalog_name".schema_name.Employees(EmployeeID) NOT ENFORCED; ALTER TABLE "catalog_name".schema_name.EmployeeDepartmentMapping ADD FOREIGN KEY (DepartmentID) REFERENCES "catalog_name".schema_name.Departments(DepartmentID) NOT ENFORCED;

10. Log in to Db2:

db2 connect to ${DBNAME}

db2 connect to oaas

db2 -t -f pkfknn.sql

db2 commit work

db2 connect reset db2 terminate

## Running queries from the Presto CLI and inspecting watsonx.datalogs

IBM watsonx.data allows running SQL queries from Presto CLI with or without using OptimizerPlus. You can also inspect the log files of the queries that are run.

## Before you begin

* 1. Install OptimizerPlus in watsonx.data. For more information, see “Installing OptimizerPlus” on page 9.

* 2. Add a presto engine connection certificate to ibm-lh-client:

./cert-mgmt --op=add --host=<host> --port=<port>

* 3. Use ibm-lh-client to upload queries where watsonx.data is configured. For example, with folder name sql-files_.

export LH_SANDBOX_DIR=<path to sql-files>

* 4. Get the list of engine names and choose the one to be used. For example with engine name engine1.

./manage-engines --op=list export engine_name=engine1

## About this task

You can select the option of running Presto CLI queries with or without using OptimizerPlus operator in watsonx.data by using the following steps. Also, watsonx.data allows inspecting the logs of the queries that are run.

## Running Presto CLI queries

## 1. Option 1: Running Presto CLI queries by using OptimizerPlus

Run the following command to run Presto queries using OptimizerPlus.

cd ibm-lh-client/ibm-lh-client/bin

./presto-run --engine=$engine_name --session enable_optimizerplus=true -f $LH_SANDBOX_DIR/simpleq.sql

* 2. Option 2: Running Presto CLI queries without using OptimizerPlus

Run the following command to run Presto queries using OptimizerPlus.

./presto-run --engine=$engine_name --session enable_optimizerplus=false -f $LH_SANDBOX_DIR/simpleq.sql

## Inspecting logs in watsonx.data

1. Run the following command to inspect the logs:

oc exec -it ibm-lh-lakehouse-presto-01-single-blue-0 bash -n cpd-instance

* tail -n 1000 /var/presto/data/var/log/server.log

* 2. Search for the text 'Before optimization'.

* 3. Map to the internal dispatcher-query-xxx.

* 4. Using the dispatcher-query-xxx, grep the line with text 'Presto successfully parsed optimized query'.

Sample response:

2023-11-23T09:42:00.391Z INFO dispatcher-query-1764 com.facebook.presto.governance.OptimizeQueryAuditAndGovernance Before optimization - --q4 2023-11-23T09:42:00.623Z INFO dispatcher-query-1764 com.facebook.presto.dispatcher.DispatchManager Presto successfully parsed optimized query

* 5. To check for query fall back, grep the line with text 'The optimisation failed(null or empty)... moving to original query' using dispatcher-query-xxx.

Sample response:

2023-11-23T09:21:58.279Z INFO dispatcher-query-1741 com.facebook.presto.dispatcher.DispatchManager The optimisation failed(null or empty)....moving to original query - --q1

## Index

## C

certificates 7 connect 4, 9, 11 connection 11

## D

database 4

## E

engine 2 Executing Presto queries 13 external 7

## I

Inspecting logs 13

## M

milvus 4, 9

## P

python 4, 9

## S

service 4

Size 2

V

vector 4
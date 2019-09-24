+++
title = "An Overview of Node Visibility in Chef Automate"
draft = false

aliases = "/visibility.html"

[menu]
  [menu.docs]
    title = "Nodes Overview"
    identifier = "legacy/chef_automate_1/overview/visibility.md Nodes Overview"
    parent = "legacy/chef_automate_1/overview"
    weight = 30
+++    

[\[edit on
GitHub\]](https://github.com/chef/chef-web-docs/blob/master/chef_master/source/visibility.rst)

<meta name="robots" content="noindex">

{{% chef_automate_mark %}}

{{% EOL_a1 %}}

Chef Automate allows you to monitor and visualize node status and
convergence events from any Chef servers or clients in your Chef
Automate cluster during a Chef Infra Client run. This data can be
filtered and searched in the UI using a simple query language. Searches
can then be shared and saved for future reference.

Setup and Configuration
=======================

Setup and configuration for node visibility is done through the
following steps:

-   Enable the node visibility feature after Chef Automate has been
    installed on a machine
-   Configure any Chef Infra Client and/or servers to connect to your
    Chef Automate server to begin ingesting data
-   (Optional) Stream event data out to a websocket consumer for further
    processing

See [Configure Data Collection](/data_collection/) for more
information on the initial setup and configuring Chef Infra Client and
server for data ingestion, and [Stream
Data](/stream_data_chef_automate/) to learn how to stream data out
for further processing.

Navigating the UI
=================

To see the node visibility capabilities of Chef Automate, log into the
Chef Automate UI and click on the **Nodes** menu item in the top nav
bar. This will open the `http://<yourAutomateServer>/viz` page, which is
the main Dashboard to visualize and filter on the data pushed to your
Chef Automate server from the Chef Infra Server and Chef Infra Clients
that have been configured to do so.

![image](/images/visibility_dashboard.png)

The left nav bar provides filtering by Chef Infra Server and
organization. The main search bar at the top provides multi-filtering
capabilities by allowing you to filter on a combination of items such as
node names, attributes, recipes, and so on. This is the main mechanism
for quickly focusing on the convergence and node data you are interested
in. The contextual help for the search bar provides a list and
explanation of how you can filter your results and the [Node Search
Query Reference](/search_query_chef_automate/) provides more details
and examples.

Further filtering can also be provided by the **Environment** and
**Roles** drop-down lists as well as the node status categories such as
**Total Nodes**, **Failed Nodes**, and so on.

If you wish to share your filtered search with others, you can do so
with the share and save icons next to the search bar.

{{< info >}}

If you want to see the raw, real-time events coming into Chef Automate
and perform simple queries and visualizations on them, navigate to
`https://<YourAutomateServer>/kibana`. Please note that as of Chef
Automate 1.6.87, Kibana is no longer enabled by default. Also, this
endpoint may be removed or restricted in a future release of Chef
Automate, so any custom dashboards or visualizations built on the Kibana
endpoint are not supported, but can be used. See the [Chef Automate
1.6.87 release
notes](https://docs.chef.io/release_notes_chef_automate.html#what-s-new-in-1-6-87)
for more details. And for more information on Kibana, see the [Kibana
User Guide](https://www.elastic.co/guide/en/kibana/current/index.html).

{{< /info >}}

Compliance status
-----------------

In addition to converge data, Chef Automate also provides information on
the compliance state of your nodes. By using Chef Automate 1.5.46 or
later, you can view compliance scan data in the **Compliance** tab at
the top of the page. See this [Overview of Compliance in Chef
Automate](/chef_automate_compliance/) for more information.

![image](/images/compliance_node.png)

This tab provides a summary of the compliance status across all nodes of
your cluster and allows you to pivot and search through that data from
either a node perspective or a profile perspective. In addition, you can
manage your compliance profiles and perform powerful filtering against
your compliance data. See the link above for more information.

Chef Automate also continues to support the reporting of compliance data
through the **Nodes** tab. If you need to continue using the previous
compliance view, you can enable it easily by typing `legacy` in the UI
and toggling on this view in the menu.
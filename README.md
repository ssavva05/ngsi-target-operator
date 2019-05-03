# NGSI Target operator

[![](https://nexus.lab.fiware.org/repository/raw/public/badges/chapters/visualization.svg)](https://www.fiware.org/developers/catalogue/)
![](https://img.shields.io/github/license/wirecloud-fiware/ngsi-target-operator.svg)

The NGSI target operator is a [WireCloud operator](http://wirecloud.readthedocs.org/en/latest/) usable for adding NGSI
subscription support to your dashboards in a simple way. Those subscriptions are a great feature provided by the
[Orion Context Broker](http://catalogue.fiware.org/enablers/publishsubscribe-context-broker-orion-context-broker).

Latest version of this operator is always
[provided in FIWARE Lab](https://store.lab.fiware.org/search/keyword/OrionStarterKit) where you can make use of it on
the [Mashup portal](https://mashup.lab.fiware.org). Remember to take a look into the example mashups provided in the
OrionStarterKit offering.

## Build

Be sure to have installed [Node.js](http://node.js). For example, you can install it on Ubuntu and Debian running the
following commands:

```console
curl -sL https://deb.nodesource.com/setup | sudo bash -
sudo apt-get install nodejs
sudo apt-get install npm
```

Install other npm dependencies by running:

```console
npm install
```

For build the widget you need download grunt:

```console
sudo npm install -g grunt-cli
```

And now, you can use grunt:

```console
grunt
```

If everything goes well, you will find a wgt file in the `dist` folder.

## Settings and Usage

### Settings

-   **NGSI server URL:** URL of the Orion Context Broker to use for retrieving entity information.
-   **NGSI proxy URL:** URL of the Orion Context Broker proxy to use for receiving notifications about changes.
-   **Use the FIWARE credentials of the user:** Use the FIWARE credentials of the user logged into WireCloud. Take into
    account this option cannot be enabled if you want to use this widget in a public workspace as anonoymous users
    doesn't have a valid FIWARE auth token. As an alternative, you can make use of the "Use the FIWARE credentials of
    the workspace owner" preference.
-   **Use the FIWARE credentials of the dashboard owner**: Use the FIWARE credentials of the owner of the workspace.
    This preference takes preference over "Use the FIWARE credentials of the user". This feature is available on
    WireCloud 0.7.0+ in a experimental basis, future versions of WireCloud can change the way to use it making this
    option not funcional and requiring you to upgrade this operator.
-   **NGSI tenant/service**: Tenant/service to use when connecting to the context broker. Must be a string of
    alphanumeric characters (lowercase) and the `_` symbol. Maximum length is 50 characters. If empty, the default
    tenant will be used
-   **NGSI scope**: Scope/path to use when connecting to the context broker. Must be a string of alphanumeric characters
    (lowercase) and the `_` symbol separated by `/` slashes. Maximum length is 50 characters. If empty, the default
    service path will be used: `/`
-   **NGSI entity types:** A comma separated list of entity types to use for filtering entities from the Orion Context
    broker. This field cannot be empty.
-   **Id pattern:** Id pattern for filtering entities. This preference can be empty, in that case, entities won't be
    filtered by id.
-   **Monitored NGSI Attributes:** Attributes to monitor for updates. Currently, the Orion Context Broker requires a
    list of attributes to monitor for changes, so this field cannot be empty.

**NOTE** If you are using a custom instance of the Orion Context Broker, take into account that by default Orion doesn't
support sending notifications to https endpoints. In those cases you can make use of a NGSI available through http at
(http://ngsiproxy.lab.fiware.org) instead of using the default one that uses https (https://ngsiproxy.lab.fiware.org).
Anyway, it is very recommended to enable the https support (see this
[link](http://stackoverflow.com/questions/23338154/orion-context-broker-https-for-subscribers) for more info about this
matter).

### Wiring

##### Input Endpoints

-   This widget has no input endpoint

##### Output Endpoints

-   **Provide entity:** This operator sends an event thought this endpoint for each entity update retrieved from the
    context broker. In addition to this, this operator send an event for every entity available initially on the context
    broker.

    In any case, event data follows the format used by the NGSI API of WireCloud for returning. E.g.

    ```json
    {
        "id": "van4",
        "type": "Van",
        "current_position": "43.47173, -3.7967205"
    }
    ```

## Copyright and License

Copyright (c) 2014-2015 CoNWeT Lab., Universidad Politecnica de Madrid

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the
License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific
language governing permissions and limitations under the License.

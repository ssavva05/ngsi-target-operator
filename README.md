# NGSI Target operator

[![](https://nexus.lab.fiware.org/repository/raw/public/badges/chapters/visualization.svg)](https://www.fiware.org/developers/catalogue/)
![](https://img.shields.io/github/license/wirecloud-fiware/ngsi-target-operator.svg)

The NGSI target operator is a [WireCloud operator](http://wirecloud.readthedocs.org/en/latest/) usable for making
context changes using the NGSI API.

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

## Documentation

Documentation about how to use this operator is available on the [User Guide](src/doc/userguide.md). Anyway, you can
find general information about how to use operators on the
[WireCloud's User Guide](https://wirecloud.readthedocs.io/en/stable/user_guide/) available on Read the Docs.

## Copyright and License

Copyright (c) 2013-2017 CoNWeT Lab., Universidad Politecnica de Madrid
Copyright (c) 2018-2019 Future Internet Consulting and Development Solutions S.L.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the
License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific
language governing permissions and limitations under the License.

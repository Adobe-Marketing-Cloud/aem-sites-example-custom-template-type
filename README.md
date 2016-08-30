# Adobe AEM 6.2 - Update pack extension: Editable template - Template Type

The current repository contains a sample _content-package_ providing a content structure illustrating the creation of a custom template type.

## Description:

The current content package provides:

* a custom page component with 
    * extra open graph meta tags with dynamic values
    * extra tab on the page properties dialog for editing open graph values
    * a base client library hook to add mandatory stylesheet and scripts
* a dedicated _/conf_ directory named _custom-template-type_
* a custom template type which
    * make use of the previous page component
* a suite of policies that
    * carry an example of configuration for the mapping of asset to component
    * different list of allowed components
    * a default page client library category hook

This package is designed to work with AEM 6.2 SP1 update pack.

## References

* [AEM Documentation: Editable Templates](https://docs.adobe.com/docs/en/aem/6-2/develop/templates/page-templates-editable.html)

## Build & Install
 
This project uses Maven for building. Common commands:

From the project directory, run ``mvn clean install -PautoInstallPackage`` to build the bundle and content package and install those to a running CQ instance.

_Avoid running the following command line ``mvn clean install content-package:install`` as it doesn't install the necessary permissions_

## Using with VLT

To use vlt with this project, first build and install the package to your local CQ instance as described above. Then cd to `src/main/content/jcr_root` and run

    vlt --credentials admin:admin co http://localhost:4502/crx/-/jcr:root . --force

Once the working copy is created, you can use the normal ``vlt up`` and ``vlt ci`` commands.
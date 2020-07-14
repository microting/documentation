# Creating a new plugin

## Basic structure and principals

Creating a new plugin is a fairly straight forward process:  
For the purpose of this example, let's call our new plugin for customers plugin, to handle a list of customers, with a simple object structure. All plugins consist of a base nuget, which is going to contain database structure and constants.

* Create a repository for your plugin in lowercase and each word seperated by "-" eg.: [eform-angular-basecustomer-plugin](https://github.com/microting/eform-angular-basecustomer-plugin)
* Create a repository for the nuget base of your plugin eg.: [eform-basecustomer-base](https://github.com/microting/eform-basecustomer-base)

### Base nuget project

The base which is going to be a nuget, needs to follow this pattern:

* A console application project called DBMigrator, with reference to the Microting.eFormBaseCustomerBase project.
* A class library called the name of your base, eg.: Microting.eFormBaseCustomerBase
* .travis.yml for testing, modify this to fit your base
* upgradeeformnugets.sh for upgrading Microting.eFormApi.BasePn and Microting.eForm

The Microting.eFormBaseCustomerBase project needs to have the following folder structure:

* Infrastructure
  * [Const](https://github.com/microting/eform-basecustomer-base/tree/master/Microting.eFormBaseCustomerBase/Infrastructure/Const)
  * Data
    * [Entities](https://github.com/microting/eform-basecustomer-base/tree/master/Microting.eFormBaseCustomerBase/Infrastructure/Data/Entities)
    * [Factories](https://github.com/microting/eform-basecustomer-base/tree/master/Microting.eFormBaseCustomerBase/Infrastructure/Data/Factories)
* [Migrations](https://github.com/microting/eform-basecustomer-base/tree/master/Microting.eFormBaseCustomerBase/Migrations)

See the basecustomer project for reference.

Keynotes to have in mind, is that every entity needs to enherit from the BaseEntity and they need to have a Versioned equivalent of the class. Each Entity needs to implement the following methods:

* public async Task Create\(CustomersPnDbAnySql dbContext\)
* public async Task Update\(CustomersPnDbAnySql dbContext\)
* public async Task Delete\(CustomersPnDbAnySql dbContext\)
* private CustomerVersion MapVersions\(CustomersPnDbAnySql dbContext, Customer customer\)  ^ replace CustomerVersion and Customer customer with the respective class names for your entity.

This is to ensure that all entities used in the ecosystem conforms to the same standard.   
See [https://github.com/microting/eform-basecustomer-base/blob/master/Microting.eFormBaseCustomerBase/Infrastructure/Data/Entities/Customer.cs](https://github.com/microting/eform-basecustomer-base/blob/master/Microting.eFormBaseCustomerBase/Infrastructure/Data/Entities/Customer.cs) for reference.

### Plugin project

The repository needs to have the following folder structure/files.

* [eform-client](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eform-client) \(for the angular part of the plugin\)
  * [e2e](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eform-client/e2e) \(for the End 2 end tests\)
  * src
    * app
      * plugins
        * modules
          * [customers-pn](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eform-client/src/app/plugins/modules/customers-pn) \(for the actual TypeScript for the plugin\)
* [eFormAPI](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn) \(for the C\# part of the project\)

  * Plugins
    * [Customers.Pn.Test](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn.Test)
    * [Customers.Pn](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn)
      * [Abstractions](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn/Abstractions)
      * [Controllers](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn/Controllers)
      * [Infrastructure](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn/Infrastructure)
        * Data
          * Seed
            * [Data](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn/Infrastructure/Data/Seed/Data)
        * [Extensions](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn/Infrastructure/Extensions)
        * [Helpers](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn/Infrastructure/Helpers)
        * [Models](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn/Infrastructure/Models)
      * [Resources](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn/Resources)
      * [Services](https://github.com/microting/eform-angular-basecustomer-plugin/tree/master/eFormAPI/Plugins/Customers.Pn/Customers.Pn/Services)

* [.travis.yml](https://github.com/microting/eform-angular-basecustomer-plugin/blob/master/.travis.yml) for testing
* [upgradeeformnugets.sh](https://github.com/microting/eform-angular-basecustomer-plugin/blob/master/upgradeeformnugets.sh) for upgrading Microting.eFormApi.BasePn, Microting.eForm and Microting.eFormBaseCustomerBase
* [testinginstallpn.sh](https://github.com/microting/eform-angular-basecustomer-plugin/blob/master/testinginstallpn.sh) for installing the route for the TypeScript part into main frontend project
* [devinstall.sh](https://github.com/microting/eform-angular-basecustomer-plugin/blob/master/devinstall.sh) for installing the plugin into the main project
* [devgetchanges.sh](https://github.com/microting/eform-angular-basecustomer-plugin/blob/master/devgetchanges.sh) for getting changes back to the repository, when changes have been done to the plugin in the main project.

See the customers project for reference.




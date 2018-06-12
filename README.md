# Way To Health HIPAA Compliance Policies

ennMedicine Way To Health, Inc ("WayToHealth") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers. As a patient engagement and health research technology organization, WayToHealth strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by WayToHealth to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for WayToHealth Customers.

WayToHealth provides secure and compliant software to administer behavioral change and patient engagement programs. Customers utilize the hosted software and infrastructure from WayToHealth to research and deploy evidence-based approches to engage patients in their health. WayToHealth makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of Customer data through network (firewalls, dedicated IP spaces, etc), server settings (encryption at rest and in transit etc), and application security requirements (password strength rules, account roles/privileges, etc).

WayToHealth does not act as a covered entity but rather as a provider of services to covered entities and other organizations. Certain aspects of our compliance are inherited from our hosting provider, Azure or Penn Medicine Academic Compute Services (PMACS), part of Penn Medicine Corporate IS as appropriate. More details about Azure's HITRUST and HIPAA compliance posture is available for review [here](https://www.microsoft.com/en-us/trustcenter/Compliance/HITRUST). Penn Medicine's policies and procedures are also incorporated into this document as relevant given that WayToHealth operates within the Penn Medicine umbrella. 

Certain aspects of compliance cannot be inherited. Because of this, WayToHealth, in order to achieve full compliance or HITRUST Certification, has implemented certain organizational policies. 

Mappings of HIPAA Rules to WayToHealth controls are covered in [§2](#2-hipaa-inheritance).

These policies are based on the open source policies published by Datica Inc. [here](https://github.com/catalyzeio/policies) and modified significantly to incorporate policies and procedures at Penn Medicine and Way To Health. 

## Install instructions

This repo can build the policies into static webpages using `Rake`. If you are using macOS, you should have Ruby pre-installed. Otherwise, make sure to [install Ruby](https://www.ruby-lang.org/en/documentation/installation/) and [RubyGems](https://rubygems.org/pages/download/). Check to make sure you have rake and bundler installed by running:
```bash
$ rake --version
# => rake, version 12.0.0
$ bundle version
# => Bundler version 1.13.7
```

If you don't have rake or bundler, run:
```bash
$ gem install rake
$ gem install bundler
```

Now we can get the repo bootstrapped. Run:
```bash
$ bundle install # installs the dependencies
```

**NOTE**: in case `bundle install` fails due to nokogiri, run the following:
```bash
$ gem uninstall nokogiri
$ xcode-select --install
$ gem install nokogiri
```

Once the dependencies have been installed, we can build the markdown files into a compliance site. Here are some of the commands you can run:
```bash
# Build files into static site with HTML, CSS, JS.
$ rake build
# Preview the compliance site on localhost:8888
$ rake serve_static
```
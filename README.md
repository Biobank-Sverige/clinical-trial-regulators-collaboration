# clinical-trial-regulators-collaboration

The common regualatory framework for clinical pharmaceutical trials within the EU/EEG area requires that the agencies involved in each member state collaborate to participate in joint evaluations of applications. To support this the involved parties in Sweden have created a set of simple systems integrations to share information and documents. This repository serves to hold specifications for structured data as well as semi structured documentation about process definitions and unstructured general descriptions of system behaviour.

This repository is created to gather technical documentation relevant to the collaboration between the Medical Products Agency, Ethical Review Authority and Biobanks in Sweden.

## structure

The purpose of this repository is first and foremost to collect common documentation in a place where it is accessable to all parties in the collaboration. The choice of platform and format is mainly due to making it accessible to buildservers and such (i.e. schema definitions).

The repository is structured according to following:
 
 * documentation/
 	* common
 		- contains general high level documentation about systems, configurations and dependencies
 	* epm
 		- contains documentation specific to the Swedish Ethical Review Authority and their handling of documents and information
 	* lv
 		- contains documentation specific to the Swedish Medical Products Agency and their handling of documents and information
 	* rbc
 		- contains documentation specific to Biobank Sweden and their handling of documents and information
 * schema
 	- contains JSON-schema definitions for the format of exchanged data



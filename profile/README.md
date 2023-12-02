# Madgrades Infrastructure Overview

## madgrades-extractor

Java binary for converting PDF files into SQL dump files for generating a relational database of course data.

## madgrades-data

Repository and archive of PDFs published by UW Madison.

GitHub actions automatically run the `madgrades-extractor` binary on these PDFs to create a Docker image which contains the SQL dump files.

## madgrades.com

JavaScript/React frontend for the website. 

GitHub actions automatically deploy changes on the main branch to `madgrades.com`, and staging branch to `staging.madgrades.com`.

## api.madgrades.com

Ruby on Rails backend for the website.

## dockerfiles

Leveraging Docker Compose, this contains Docker configurations for running the Madgrades API and all necessary dependencies in containers.

It also contains scripts to seed the database with fresh data if a new `madgrades-data` image is specified.

GitHub actions automatically deploy the changes to production. There is no staging branch.

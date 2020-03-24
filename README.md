## INFO
This is a fork from https://github.com/noelob/jmeter-gradle-plugin who is a fork from foraggerr's jmeter-gradle-plugin.  Both have done great work, one adjustment made in this repo is publishing to local maven repo only target/support as a gradle-plugin as traditional jar builds/deploys are insufficient.

Run:
 
     gradle publish

## SAMPLE USAGE/CONSUMPTION in another project

build.gradle

    buildscript {
      repositories {
        mavenLocal() //needed to load/use local maven repo plugins (testing jmeter plugin for example)
        ...
      }
      dependencies {
        classpath "io.quintessent.jmeter:jmeter-gradle-plugin:1.1.2-5.0-20200324"
        ...
      }
    }
    plugins {
        id "io.quintessent.jmeter" version "1.1.2-5.0-20200324"
        ...
    }
    jmeter {
      jmTestFiles = [file("jmeter/mytest.jmx"),file("jmeter/mytest2.jmx")]
      //jmSystemPropertiesFiles = [file("jmeter/jmeter.properties")]
      enableExtendedReports = true
    }
    

Then execute:
   
    gradle jmRun
    --or--
    gradle jmGui    

## LEGACY README BELOW


## Gradle plugin to execute JMeter tests.  
[![Build Status](https://travis-ci.org/noelob/jmeter-gradle-plugin.svg?branch=master)](https://travis-ci.org/jmeter-gradle-plugin/jmeter-gradle-plugin) [ ![Download](https://api.bintray.com/packages/noelob/gradle-plugins/jmeter-gradle-plugin/images/download.svg) ](https://bintray.com/noelob/gradle-plugins/jmeter-gradle-plugin/_latestVersion)

For usage see: http://jmeter.foragerr.net/  
or [wiki](https://github.com/jmeter-gradle-plugin/jmeter-gradle-plugin/wiki/Getting-Started)

## News
**03 Dec 2019**
* Version 1.1.1 released with support for JMeter 5.0
* I have not extensively tested this release, caveat emptor

## Attribution
This project started as a hard fork of [jmeter-gradle-plugin/jmeter-gradle-plugin](https://github.com/jmeter-gradle-plugin/jmeter-gradle-plugin). Besides defect fixes and feature enhancements, most of the original codebase is intact. 

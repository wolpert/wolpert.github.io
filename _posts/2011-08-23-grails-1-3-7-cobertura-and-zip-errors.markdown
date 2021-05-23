---
author: wolpert
comments: true
date: 2011-08-23 17:09:20+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2011/08/23/grails-1-3-7-cobertura-and-zip-errors/
slug: grails-1-3-7-cobertura-and-zip-errors
title: Grails 1.3.7, cobertura and zip errors
wordpress_id: 288
---

When turning code-coverage on for my grails app, I suddenly started getting an error when cobertura was instrumenting my classes; unable to read zip file. Found someone with similar issues [here](http://comments.gmane.org/gmane.comp.lang.groovy.grails.user/106477), but I had to end up with a different patch. I added the closure onto the fileset request on line 122 of _GrailsClasspath.groovy. Yeah, its a grails problem... they assume everything is a jar or zip in a lib directory... guess its not true in a plugin I loaded. Anyways, here's the patch I added:

    
        for (pluginLib in pluginLibDirs) {
            fileset(dir: pluginLib.file.absolutePath){
                include(name:"**/*.jar") 
                include(name:"**/*.zip")
            }   
        }

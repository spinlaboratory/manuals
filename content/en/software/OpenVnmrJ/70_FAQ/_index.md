---
title:        "Frequently Asked Questions"
linkTitle:    "FAQ"
type:         docs
weight:       70
draft:        false
description:  "Frequently asked questions"
---




### Check the B12T SCN ###

1. Reset the connection to the SCN with the command
    {{<highlight shell>}}
    B12SCNControl('reset')
    {{</highlight>}}

2. Check the state and connection for the SCN with the command
    {{<highlight shell>}}
    B12SCNControl('state?')
    {{</highlight>}}

    If everything is connected OVJ will return

    {{<highlight shell>}}
    'intamp'
    {{</highlight>}}
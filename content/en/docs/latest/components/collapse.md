---
author: Mark Dumay
title: Collapse
date: 2023-05-21
description: Use the collapse shortcode to reveil or hide a panel.
layout: docs
icon: fa eye-slash
tags: component
---

## Overview

Use the `collapse` shortcode to reveil or hide a panel. The panel can contain both HTML code and plain text. Link a button to the panel by assigning it's ID to the `collapse` attribute. As an example, the following shortcode displays a button that, when clicked, triggers a panel to appear or disappear.

<!-- markdownlint-disable MD037 -->
{{< example lang="hugo" >}}
{{</* button collapse="collapse-1" */>}}
    Trigger panel
{{</* /button */>}}

{{</* collapse id="collapse-1" class="p-3 border rounded" */>}}
    Some placeholder content for the collapse component. This panel is <i>hidden by default</i> but
    revealed when the user activates the relevant trigger.
{{</* /collapse */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->

## Arguments

The shortcode supports the following arguments:

{{< table >}}
| Argument    | Required | Description |
|-------------|----------|-------------|
| id          | Yes      | Required unique id of the collapse element, e.g. "collapse-1". |
| class       | No       | Optional class attribute of the inner panel element, e.g. “p-3”. |
{{< /table >}}

## Remarks

The [nav shortcode]({{< relref "navs-and-tabs" >}}) uses multiple collapse panels under the hood to provide access to a group of tab panes.
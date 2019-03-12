# Feedback for Prisma Admin

This repository is the central place to collect feedback and issues related to [Prisma Admin](https://www.prisma.io/admin).

Please [**open an issue**](https://github.com/prisma/prisma-admin-feedback/issues/new) if you want to leave feedback.

## Custom components

Custom components are a powerful extension of the Prisma Admin UI. They allow you to provide a custom UI for displaying your data. 

### Custom component example

This example shows a custom component for a `User` record that renders certain fields in a customized way, e.g. the `location` is displayed as a map and the `permissions` are rendered as single tags.

![](https://i.imgur.com/yZ8MosF.png)

### How custom components works

Custom components are standard [`iframe`](https://en.wikipedia.org/wiki/HTML_element#Frames) HTML elements which render your data in a custom way. Prisma Admin provides the data for a specific database record to your custom component trough a query string: `${url}?data=${JSON.stringify(data)}`. It's possible to have multiple view for single query. Here is basic [example](https://github.com/Huvik/Custom-view) for json custom view.

### How to add a custom component in Prisma Admin 

1. In the **Detail area**, click the little button that looks like an eye
1. Click **Add a view** 
1. Add custom component info:
    - Name: A name for the custom component (e.g. `MyUserView`)
    - URL:  The HTTP endpoint where the `iframe` element is being served. Note that Prisma Admin will append the corresponding database record as JSON to the URL as the query string.

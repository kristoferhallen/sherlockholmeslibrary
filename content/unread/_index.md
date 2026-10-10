---
title: Unread books
# Books in a series that are not reviewed yet. They have no pages of their
# own; the reading guides list them. To turn one into a review, move the
# bundle to content/posts/ and add date, grade, description, tags and text.
build:
  render: never
  list: never
cascade:
  build:
    render: never
    list: local
    publishResources: false
---

# Dash Browser Framework
This repository hosts a set of pre-written tools, components, and templates to enable building
Dash apps with similar UIs. The core UI is built of three components:
- A plugin selector which acts as a full-width header
- A source selector pane below the header, occupying the left 3rd of the page
- A display pane below the header, to the right of the file selector

The display pane is driven entirely by the selections in the other two components.
The source selector determines what data you want to operate on and the plugin determines
what the operation will be.
There are a variety of ways to populate the plugin and source selector components. As examples, the plugin selector could be radio buttons,
dropdowns, or multi-selections. The source selector could be a local file system browser, a text field, or a SQL query.

You can view the entire process as a pipeline that flows as:
- Select data source
- Send data source to selected plugin
- Perform operation/transformation/analysis with plugin
- Plugin outputs a Dash `Component`
- The component is rendered in the display pane

## When could Dash Browser be useful?
- Plugins help traverse different data representations quickly
- The operations on the data that you want to perform are relatively fast (<= O(seconds))
- Your data sources can fit in memory
- You don't want to have to write a bunch of Dash components -- and anything you do write could be added to this framework
- You want to iterate quickly on views of your data
- You want to be able to host the plugin logic and enable others to view their own data

## When would Dash Browser be a bad idea?
- Your data sources don't fit in memory
- Your operations are very slow to run
- You have just one operation you want to perform
  - Use a python notebook
- You never plan on doing the analyses you're thinking of (the potential plugin) more than a few times
  - Use a python notebook
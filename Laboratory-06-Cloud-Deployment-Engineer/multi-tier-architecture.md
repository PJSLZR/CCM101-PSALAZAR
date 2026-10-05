# Research: Two-Tier Architecture

## The Web/Application Tier

This tier runs the Nextcloud application itself. It serves the user interface, handles incoming HTTP requests from browsers, processes file uploads and downloads, and contains the business logic of the app. It does not permanently store structured data itself — it depends on the database tier for that.

## The Database Tier

This tier runs MariaDB. Its role is to store persistent, structured data: user accounts, credentials, permissions, and file metadata (filenames, folders, sharing links, timestamps). It does not serve any content to end users directly; only the application tier talks to it.

## Why Separate Them?

Separating the web tier and the database tier into their own containers means each one can be scaled, updated, backed up, or restarted independently without affecting the other. If the web application needs more resources during high traffic, only that container has to scale, while the database stays untouched. It also improves security, since the database never has to be exposed directly to the internet, and failures are isolated: a crash in the app container doesn't take the stored data down with it.

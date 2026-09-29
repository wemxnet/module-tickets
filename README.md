# Tickets

Customer support tickets for WemX. Customers open tickets from the client area, staff work them from an inbox, and departments control routing, guest access, and auto-close.

## Features

- Client ticket list, create form, and conversation
- Staff inbox with assignment, priority, department, and status
- Departments with prefill templates, auto-responses, and a notify address
- Guest tickets with a private access link
- Invite participants, and let members subscribe or unsubscribe
- Internal notes that stay off the customer thread
- Lock a ticket so only staff can reply
- Attach a ticket to an order
- Email notifications, with reply-by-email
- Hourly auto-close when a ticket has been waiting on the customer
- Widgets on the client dashboard, order pages, the admin dashboard, and the customer profile

Default departments: General Support, Technical Support, Billing, Sales, and Abuse.

## Install

Install from the WemX marketplace, or place this repository at `extensions/Modules/Tickets` and enable **Tickets**.

Enabling the module runs its migrations, adds the admin permissions, and creates the default departments. Uninstalling keeps existing ticket data.

## Email replies

On **Admin → Tickets → Departments**, set the inbound mailbox. Outbound mail uses a plus-address on that mailbox, for example `support+t12.ab12cd34@yourdomain.com`.

Forward or pipe that mailbox into WemX:

- POST the raw message to the webhook URL shown on the same page, or
- Pipe it to `php artisan tickets:ingest-mail`

Unknown senders, duplicate messages, and empty bodies are ignored.

## Permissions

| Permission | Access |
| --- | --- |
| `admin.tickets` | Inbox |
| `admin.tickets.view` | View and reply |
| `admin.tickets.create` | Open a ticket for a customer |
| `admin.tickets.update` | Department, priority, assignment, and status |
| `admin.tickets.delete` | Delete tickets |
| `admin.ticket-departments` | View departments |
| `admin.ticket-departments.create` | Create departments |
| `admin.ticket-departments.update` | Update departments |
| `admin.ticket-departments.delete` | Delete departments |

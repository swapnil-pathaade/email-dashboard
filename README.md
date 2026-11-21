# email-dashboard

Sending application emails gets harder when you need reusable templates, several SMTP accounts, and delivery schedules across time zones. email-dashboard puts those tasks in a web dashboard where you can also review outgoing email activity.

## Features

- Monitor outgoing email activity from your applications.
- Create reusable email templates in the dashboard.
- Configure multiple SMTP connections.
- Schedule email delivery with time zone support.
- Run scheduled activities immediately or cancel them.

**Email tracking and A/B testing are not implemented.** They are listed as planned features in the upstream project.

## Installation

The dashboard uses Ruby on Rails; the REST API uses Go. The upstream deployment also uses MySQL and Redis. You need those services and the API configured alongside the dashboard for the complete application.

With the repository checked out, run these commands from the Rails application directory. Use the Ruby version specified by the project and a compatible Bundler version:

```bash
bundle install
```

Review the checkout's environment settings and database configuration. Set your local database credentials and service addresses before creating the database:

```bash
bundle exec rails db:create
bundle exec rails db:migrate
```

Configure SMTP connections with credentials for your mail provider. Keep credentials out of version control, and use a test SMTP account during development.

## Usage

Start the Rails dashboard locally:

```bash
bundle exec rails server --binding 127.0.0.1 --port 3000
```

Open http://127.0.0.1:3000. With the required services configured and running, use the dashboard to create templates, configure SMTP connections, and schedule outgoing email. Review scheduled activities to run them immediately or cancel them.

This command starts the dashboard only; it does not start the Go API, MySQL, or Redis.

## License

MIT. email-dashboard is based on [Email-Dashboard/Email-Dashboard](https://github.com/Email-Dashboard/Email-Dashboard), which is also MIT-licensed. Retain the upstream copyright notice and MIT permission notice when distributing copies or substantial portions of the code.


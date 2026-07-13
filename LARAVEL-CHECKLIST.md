# Laravel Script Purchase and Audit Checklist

Use this checklist before purchasing, deploying or customizing a Laravel application, script, starter kit or self-hosted platform.

This checklist is intended for developers, agencies, founders and technical teams evaluating Laravel source code before using it in production.

## 1. Product scope

* [ ] The product is clearly identified as a complete application, starter kit, package, module or template.
* [ ] The intended use case is clearly explained.
* [ ] Included functionality is documented.
* [ ] Excluded functionality is documented.
* [ ] Screenshots or a working live demo are available.
* [ ] The product is actively maintained.
* [ ] The last update date is visible.
* [ ] The supported Laravel version is specified.
* [ ] The supported PHP version is specified.

## 2. Laravel and PHP compatibility

* [ ] The exact Laravel version is documented.
* [ ] The minimum PHP version is documented.
* [ ] Required PHP extensions are listed.
* [ ] Composer requirements are documented.
* [ ] The application does not depend on abandoned Composer packages.
* [ ] Package versions are compatible with the required Laravel version.
* [ ] The application can be installed using a standard Composer workflow.
* [ ] Upgrade instructions are available for future Laravel versions.
* [ ] The product does not require unsupported or end-of-life PHP versions.

## 3. Project structure

* [ ] The application follows a clear Laravel directory structure.
* [ ] Controllers do not contain excessive business logic.
* [ ] Business logic is separated into services, actions or domain classes where appropriate.
* [ ] Validation is handled through Form Request classes or equivalent validation logic.
* [ ] Authorization is implemented through policies, gates or middleware.
* [ ] Reusable logic is not duplicated unnecessarily.
* [ ] Models do not contain excessive unrelated responsibilities.
* [ ] Routes are organized logically.
* [ ] Configuration values are stored in configuration files.
* [ ] Environment-specific values are stored in `.env`.

## 4. Environment configuration

* [ ] A complete `.env.example` file is included.
* [ ] Sensitive credentials are not committed to the repository.
* [ ] Required environment variables are documented.
* [ ] Production and development settings are clearly separated.
* [ ] `APP_DEBUG` can be disabled for production.
* [ ] `APP_ENV` is configured correctly.
* [ ] `APP_KEY` generation is documented.
* [ ] Mail configuration is documented.
* [ ] Queue configuration is documented.
* [ ] Cache configuration is documented.
* [ ] Storage and filesystem configuration is documented.

## 5. Database

* [ ] The supported database system is specified.
* [ ] Database version requirements are documented.
* [ ] Laravel migrations are included.
* [ ] Migrations can run on a clean database.
* [ ] Migration rollback is supported where practical.
* [ ] Seeders or demo data are included when needed.
* [ ] Foreign keys and indexes are defined correctly.
* [ ] Database queries avoid unnecessary N+1 problems.
* [ ] Large result sets use pagination or chunking.
* [ ] Sensitive data is not stored in plain text.
* [ ] Database schema changes are documented in the changelog.

## 6. Authentication

* [ ] Authentication functionality is clearly documented.
* [ ] Passwords are stored using Laravel-supported hashing.
* [ ] Password reset functionality works correctly.
* [ ] Email verification is implemented when required.
* [ ] Login attempts are rate limited.
* [ ] Session settings are suitable for production.
* [ ] Remember-me functionality is implemented securely.
* [ ] User registration can be disabled if the application requires it.
* [ ] Inactive or suspended users are handled correctly.
* [ ] Authentication routes are protected against abuse.

## 7. Authorization and roles

* [ ] User roles are clearly documented.
* [ ] Permissions are enforced on the server side.
* [ ] Admin routes are protected by authorization middleware.
* [ ] Policies or gates are used for resource-level permissions.
* [ ] Users cannot access records belonging to other users without permission.
* [ ] Role changes are logged where appropriate.
* [ ] Privilege escalation is prevented.
* [ ] API endpoints apply the same authorization rules as web routes.

## 8. Input validation

* [ ] All user input is validated.
* [ ] Validation rules are centralized where practical.
* [ ] File uploads validate file type, extension and size.
* [ ] HTML input is sanitized when rich text is supported.
* [ ] Numeric values are validated correctly.
* [ ] Date and time inputs are validated.
* [ ] Enum-like values are restricted to allowed options.
* [ ] API requests use the same validation quality as web forms.
* [ ] Validation errors are displayed safely.
* [ ] Mass assignment protection is configured correctly.

## 9. File uploads and storage

* [ ] Upload directories are documented.
* [ ] Allowed file types are restricted.
* [ ] File size limits are enforced.
* [ ] Uploaded filenames are sanitized or replaced.
* [ ] Files cannot be uploaded into executable public locations without protection.
* [ ] Private files use protected storage.
* [ ] File access is authorized.
* [ ] Deleted records remove related files where appropriate.
* [ ] Storage linking requirements are documented.
* [ ] Cloud storage configuration is documented if supported.

## 10. Security

* [ ] CSRF protection is enabled.
* [ ] SQL queries use Eloquent, Query Builder or parameter binding.
* [ ] Raw SQL usage is reviewed carefully.
* [ ] Blade output is escaped by default.
* [ ] Unescaped HTML is used only when required and sanitized.
* [ ] Authentication endpoints are rate limited.
* [ ] Sensitive routes require authorization.
* [ ] API tokens are stored securely.
* [ ] Secrets are not exposed in frontend JavaScript.
* [ ] Debug information is disabled in production.
* [ ] Error pages do not expose sensitive information.
* [ ] Security headers can be configured.
* [ ] Dependencies have been checked for known vulnerabilities.
* [ ] The application has not been advertised as fully secure without an independent audit.

## 11. Composer dependencies

* [ ] `composer.json` is included.
* [ ] `composer.lock` is included for application projects.
* [ ] Dependencies are actively maintained.
* [ ] No abandoned packages are used without explanation.
* [ ] Package licenses are compatible with the product license.
* [ ] Private packages are documented.
* [ ] Post-install scripts are reviewed.
* [ ] Composer scripts do not perform unsafe operations.
* [ ] Dependency installation does not require undocumented credentials.
* [ ] `composer audit` can be run successfully or known issues are disclosed.

## 12. Frontend stack

* [ ] The frontend technology is specified.
* [ ] Node.js version requirements are documented.
* [ ] The package manager is specified.
* [ ] `package.json` is included.
* [ ] Lock files are included.
* [ ] Build commands are documented.
* [ ] Production assets can be built successfully.
* [ ] Development assets can be started locally.
* [ ] Frontend dependencies are reasonably current.
* [ ] The application does not depend on undocumented premium packages.
* [ ] The responsive behavior is documented.
* [ ] Browser compatibility is documented.

## 13. Queues

* [ ] The application documents whether queues are required.
* [ ] The queue driver is specified.
* [ ] Queue worker commands are documented.
* [ ] Failed jobs are handled.
* [ ] Retry behavior is configured.
* [ ] Long-running tasks are moved out of web requests.
* [ ] Jobs are idempotent where necessary.
* [ ] Queue monitoring is recommended for production.
* [ ] Supervisor or equivalent worker configuration is documented.
* [ ] Queue-related environment variables are included in `.env.example`.

## 14. Scheduler and cron

* [ ] Required scheduled tasks are documented.
* [ ] The Laravel scheduler command is provided.
* [ ] The production cron entry is documented.
* [ ] Scheduled tasks do not overlap unexpectedly.
* [ ] Long-running scheduled tasks use appropriate locking.
* [ ] Time zone assumptions are documented.
* [ ] Failed scheduled tasks are logged.
* [ ] Optional and mandatory scheduled tasks are clearly distinguished.

## 15. Cache and sessions

* [ ] Supported cache drivers are documented.
* [ ] Supported session drivers are documented.
* [ ] Cache invalidation is handled correctly.
* [ ] User-specific data is not cached globally.
* [ ] Redis requirements are documented if applicable.
* [ ] Session security settings are suitable for production.
* [ ] Session expiration behavior is documented.
* [ ] Cache clearing commands are documented.
* [ ] Configuration and route caching work correctly.

## 16. Email and notifications

* [ ] Required mail configuration is documented.
* [ ] Email templates are included.
* [ ] Email sending failures are handled.
* [ ] Email jobs use queues when appropriate.
* [ ] Notification channels are documented.
* [ ] Third-party email services are identified.
* [ ] Sender addresses are configurable.
* [ ] Unsubscribe requirements are addressed where applicable.
* [ ] Email preview or testing instructions are included.

## 17. API

* [ ] The product clearly states whether an API is included.
* [ ] API authentication is documented.
* [ ] API routes are versioned where appropriate.
* [ ] API permissions are enforced.
* [ ] Input validation is implemented.
* [ ] Rate limiting is configured.
* [ ] API error responses are consistent.
* [ ] API documentation is available.
* [ ] Sensitive fields are excluded from API responses.
* [ ] CORS configuration is documented.
* [ ] API tokens can be revoked.

## 18. Third-party services

* [ ] All external services are listed.
* [ ] Required API keys are documented.
* [ ] Pricing or usage limits of external services are disclosed.
* [ ] The product works without undocumented external accounts.
* [ ] Webhook configuration is documented.
* [ ] Webhook signatures are validated.
* [ ] Failure handling is implemented.
* [ ] External service timeouts are configured.
* [ ] Vendor lock-in risks are understood.
* [ ] Sandbox or test environments are supported where relevant.

## 19. Payments

* [ ] Supported payment gateways are listed.
* [ ] Gateway-specific requirements are documented.
* [ ] Test and production modes are separated.
* [ ] Webhook verification is implemented.
* [ ] Payment status is validated on the server side.
* [ ] Sensitive payment data is not stored unnecessarily.
* [ ] Refund behavior is documented.
* [ ] Currency handling is documented.
* [ ] Taxes and fees are handled transparently.
* [ ] Payment-related legal responsibilities are not misrepresented.
* [ ] The seller does not claim regulatory compliance without evidence.

## 20. Installation

* [ ] Installation documentation is included.
* [ ] Required server software is listed.
* [ ] Required PHP extensions are listed.
* [ ] Composer installation steps are documented.
* [ ] Frontend build steps are documented.
* [ ] Database creation steps are documented.
* [ ] Migration and seeding steps are documented.
* [ ] Storage permissions are documented.
* [ ] Storage linking is documented.
* [ ] Cron configuration is documented.
* [ ] Queue worker configuration is documented.
* [ ] Web server configuration is documented.
* [ ] SSL requirements are documented.
* [ ] Installation can be completed on a clean server.

## 21. Web server and hosting

* [ ] Supported web servers are documented.
* [ ] Apache rewrite requirements are included.
* [ ] Nginx configuration guidance is included.
* [ ] The public directory is configured as the document root.
* [ ] Required file permissions are documented.
* [ ] Minimum memory and storage requirements are documented.
* [ ] Shared hosting compatibility is explained.
* [ ] VPS requirements are explained.
* [ ] HTTPS is supported and recommended.
* [ ] Background process requirements are documented.

## 22. Logging and monitoring

* [ ] Application errors are logged.
* [ ] Sensitive values are excluded from logs.
* [ ] Log rotation is documented.
* [ ] Failed jobs are observable.
* [ ] Payment and security-sensitive actions are logged.
* [ ] Audit logging is included where appropriate.
* [ ] Production monitoring recommendations are provided.
* [ ] Health checks are available where relevant.

## 23. Testing

* [ ] Automated tests are included or their absence is disclosed.
* [ ] Test setup instructions are documented.
* [ ] Critical business logic is covered.
* [ ] Authentication and authorization are tested.
* [ ] Payment workflows are tested where relevant.
* [ ] API endpoints are tested where relevant.
* [ ] Database tests can run safely.
* [ ] Test credentials are not production credentials.
* [ ] The test suite can run on a clean installation.

## 24. Code customization

* [ ] Branding can be changed.
* [ ] Application name and logo are configurable.
* [ ] Colors and theme settings are documented.
* [ ] Email templates can be customized.
* [ ] Business rules are separated from presentation logic.
* [ ] Translations are supported where claimed.
* [ ] Custom modules can be added without modifying core files excessively.
* [ ] Update-safe customization guidance is available.
* [ ] Customization limitations are disclosed.

## 25. Documentation

* [ ] A getting-started guide is included.
* [ ] Installation documentation is complete.
* [ ] Configuration options are documented.
* [ ] Environment variables are documented.
* [ ] Common errors are documented.
* [ ] Queue and cron requirements are documented.
* [ ] API documentation is included where relevant.
* [ ] Customization instructions are included.
* [ ] Update instructions are included.
* [ ] A changelog is available.
* [ ] Documentation matches the current product version.

## 26. Updates

* [ ] The update policy is clearly explained.
* [ ] The period of included updates is specified.
* [ ] Update installation steps are documented.
* [ ] Database changes are included in migrations.
* [ ] Breaking changes are identified.
* [ ] The changelog includes meaningful details.
* [ ] Custom changes are considered before updating.
* [ ] Previous versions are available where appropriate.
* [ ] Security updates are handled promptly.

## 27. Support

* [ ] The support period is clearly stated.
* [ ] Support channels are listed.
* [ ] Expected response times are documented.
* [ ] Installation support is explained.
* [ ] Bug-fix support is explained.
* [ ] Customization support is explained.
* [ ] Third-party integration support is explained.
* [ ] Unsupported requests are listed.
* [ ] Paid custom development is separated from standard support.

## 28. License

* [ ] The license type is clearly identified.
* [ ] Commercial use is explained.
* [ ] Client-project use is explained.
* [ ] Domain or project limits are explained.
* [ ] Source-code modification rights are explained.
* [ ] Resale rules are explained.
* [ ] Redistribution rules are explained.
* [ ] Third-party package licenses are compatible.
* [ ] Fonts, images and other assets have valid licenses.
* [ ] The license does not conflict with open-source dependencies.
* [ ] The buyer understands which rights are not transferred.

## 29. Seller credibility

* [ ] The seller has a complete profile.
* [ ] The seller has previous work that can be reviewed.
* [ ] Contact information is available.
* [ ] Support history is visible.
* [ ] Update history is visible.
* [ ] Reviews appear authentic.
* [ ] Product claims can be verified.
* [ ] The seller responds to technical questions.
* [ ] The seller can explain the architecture and requirements.

## 30. Production readiness

* [ ] Production debug mode is disabled.
* [ ] Environment secrets are configured securely.
* [ ] HTTPS is enabled.
* [ ] Backups are configured.
* [ ] Queue workers are supervised.
* [ ] Scheduled tasks are configured.
* [ ] Storage permissions are correct.
* [ ] Logging and monitoring are enabled.
* [ ] Error reporting is configured.
* [ ] Dependencies have been audited.
* [ ] Default passwords have been changed.
* [ ] Demo data has been removed or secured.
* [ ] Admin access is protected.
* [ ] The application has been tested in a staging environment.
* [ ] A security review has been completed before handling sensitive data.

## 31. Final decision

Before purchasing or deploying the Laravel product, confirm:

* [ ] The application supports the required Laravel and PHP versions.
* [ ] All required dependencies are documented.
* [ ] The code structure is maintainable.
* [ ] Installation has been tested.
* [ ] Security-sensitive areas have been reviewed.
* [ ] The license matches the intended use.
* [ ] Update and support terms are acceptable.
* [ ] Third-party service costs are understood.
* [ ] No critical technical questions remain unresolved.

Do not deploy a Laravel script to production until its code, dependencies, configuration, security and licensing have been independently reviewed.

## Disclaimer

This checklist does not replace:

* a professional source-code audit,
* penetration testing,
* legal advice,
* regulatory compliance review,
* production infrastructure assessment.

The buyer remains responsible for validating the product before purchasing, modifying or deploying it.

## About esdecode

This checklist is maintained by [esdecode](https://esdecode.com), a marketplace for scripts, plugins, applications, templates and other source-code products.

Explore Laravel products and developer resources at [esdecode.com](https://esdecode.com).

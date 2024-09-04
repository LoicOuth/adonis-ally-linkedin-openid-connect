# AdonisJS LinkedIn OpenID Connect Ally Driver
This package provides an Ally driver for AdonisJS to integrate LinkedIn’s OpenID Connect authentication method. It enables seamless user login through LinkedIn, using the industry-standard OpenID Connect protocol according to their [documentation](https://learn.microsoft.com/en-us/linkedin/shared/authentication/authentication). Perfect for applications that need to authenticate users via their LinkedIn accounts while securely handling the OpenID Connect flow.

# Installation

```bash
npm install adonis-linkedin-openid
```

Add this lines in `config/ally.ts`
```typescript
import env from '#start/env'
import { defineConfig } from '@adonisjs/ally'
import { LinkedinOpenidConnectService } from 'adonis-ally-linkedin-openid-connect'

const allyConfig = defineConfig({
  linkedinOpenidConnect: LinkedinOpenidConnectService({
    clientId: env.get('LINKEDIN_CLIENT_ID'),
    clientSecret: env.get('LINKEDIN_CLIENT_SECRET'),
    callbackUrl: env.get('LINKEDIN_CALLBACK_URL'),
  }),
})
```

Now you can use it in your application 
```typescript
const linkedin = ally.use('linkedinOpenidConnect')
```

# Resources

[Linkedin openid connect documentation](https://learn.microsoft.com/en-us/linkedin/shared/authentication/authentication)

[Adonis ally documentation](https://docs.adonisjs.com/guides/authentication/social-authentication)



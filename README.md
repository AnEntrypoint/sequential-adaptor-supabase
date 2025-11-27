# Sequential Adaptor Supabase

Supabase PostgreSQL storage backend for sequential-ecosystem.

## Installation

```bash
npm install sequential-adaptor sequential-adaptor-supabase
```

## Usage

```javascript
import { SupabaseAdapter } from 'sequential-adaptor-supabase';
import { TaskExecutor } from 'sequential-adaptor';

const adapter = new SupabaseAdapter(
  'https://your-project.supabase.co',
  'your-service-key',
  'your-anon-key'
);

await adapter.init();

const executor = new TaskExecutor(adapter);
```

## Via Registry

```javascript
import { createAdapter } from 'sequential-adaptor';

const adapter = await createAdapter('supabase', {
  url: process.env.SUPABASE_URL,
  serviceKey: process.env.SUPABASE_SERVICE_KEY,
  anonKey: process.env.SUPABASE_ANON_KEY
});
```

## Environment Variables

```bash
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_KEY=your-service-key
SUPABASE_ANON_KEY=your-anon-key
```

## Database Schema

Tables created by migrations:
- `task_runs` - Task execution records
- `stack_runs` - Service call records
- `task_functions` - Published task code
- `keystore` - Credentials

## Features

- Managed PostgreSQL database
- Scalable for production use
- Real-time capabilities via Supabase

## License

MIT

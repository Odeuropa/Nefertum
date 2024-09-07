# Nefertum

Akinator like guesser for smells.

- Demo available at https://nefertum.odeuropa.eu/
- View feedbacks at https://nefertum.odeuropa.eu/feedbacks
- View community added sources at https://nefertum.odeuropa.eu/added-sources
- Clear matrixes at https://nefertum.odeuropa.eu/clear-matrixes

## How to deploy for production

1. Copy the file `.env.example` into `.env` and edit it accordingly:

   - `API_PORT` - Port for the API (default: 5000)
   - `CLIENT_PORT` - Port for the client (default: 3000)
   - `NEXT_PUBLIC_API_ENDPOINT` - URL to the API endpoint
   - `NEXT_PUBLIC_SUPABASE_URL` - URL to the Supabase database
   - `NEXT_PUBLIC_SUPABASE_ANON_KEY` - Supabase anon

1. Download the [smell embeddings](https://data.odeuropa.eu/image/smell_embeddings/voc.kv) and copy them into the `api/data` directory.

1. Run the following command:

   ```bash
   docker compose up --build -d
   ```

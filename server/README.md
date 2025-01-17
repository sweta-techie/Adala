# run in Docker

## setup config

```bash
cp .env.example .env
```

## set environment variables

- AWS creds:
```bash
eval "$(aws configure export-credentials --profile <YOUR_PROFILE> --format env)"
```

## run

```bash
# from repo root
docker-compose up
```


## rebuild and run on code change

```bash
# from repo root
docker-compose up --build
```

## run client

```bash
cd ui/
yarn start
```

# development

## edit client on API change

```bash
./api_codegen.sh
export SERVER=$(pwd)
cd ui/
yarn codegen
```
now edit `src/adala.tsx` manually given the autogenerated changes in `src/_api/`

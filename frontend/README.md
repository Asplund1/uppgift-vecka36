uppgifter till vecka 36

uppgift 1-7
# CI/CD med Docker och GitHub Actions

## Uppgift 1 – Första CI-pipeline
- Skapade en `ci.yml` som körs på `dev`-branchen.
- Pipelinen bygger en Docker-image för frontend automatiskt när jag pushar kod.
- Lärdom: Actions kan automatiskt bygga images vid varje commit.

## Uppgift 2 – Automatiserade tester
- Lagt till Jest-tester i frontend och integrerat `npm test` i pipelinen.
- Testerna körs automatiskt i containern efter build.
- Lärdom: pipelinen stoppar om testerna misslyckas så det är en bra kvalitetssäkring.

## Uppgift 3 – Flera tjänster i samma pipeline
- Lagt till både frontend och api i samma jobb i `ci.yml`.
- Båda tjänsterna byggs och tester körs i turordning.
- Lärdom: en pipeline kan hantera flera tjänster, men körningstiden ökar.

## Uppgift 4 – Parallell exekvering
- Delade upp frontend och api i två olika jobb.
- Jobben körs parallellt i Actions.
- Lärdom: körtiden minskar när flera jobb kan köras samtidigt.

## Uppgift 5 – Pipelinefel
- La medvetet in ett fel i ett test.
- Såg i Actions-loggen exakt vilket test som misslyckades.
- Fixade felet och verifierade att pipelinen blev grön igen.
- Lärdom: loggarna i Actions är tydliga för felsökning.

## Uppgift 6 – Versions-taggar
- Byggde och pushade `dockerasplund/frontend:v1.0.0` och `dockerasplund/frontend:v1.1.0`.
- Testade att byta mellan versionerna i `docker-compose.yml`.
- Lärdom: `:latest` är bekvämt men osäkert, versions-taggar är mer stabila och lättare att förstå.

## Uppgift 7 – Multi-stage Dockerfile
- Skapade en Dockerfile med två steg: builder/test och runtime.
- Builder-stegen kör tester och innehåller dev-beroenden.
- Runtime-stegen är liten och ren, och endast den pushas till Docker Hub.
- Fördelar: mindre, snabbare och säkrare images.
- Reflektion: bättre att underhålla en multi-stage Dockerfile än flera separata filer för dev/prod.

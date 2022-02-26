# YouTubeOpenAPI
OpenAPI bindings for YouTube (and YouTube Music) internal API, also called InnerTube.

# Usage
This is using YML syntax to specify responses and requests, defined by the [OpenAPI spec](https://www.openapis.org/).

You can transcompile (auto-generate bindings) this YML file to practicaly any programming language. You should use [swagger-codegen](https://github.com/swagger-api/swagger-codegen), as I personally had issues with [openapi-generator](https://openapi-generator.tech/).

# Generate Dart SDK
Dart SDK can be generated using [openapi-generator](https://openapi-generator.tech/). Install it using NPM and run following command:
```sh
npx @openapitools/openapi-generator-cli generate -i ytmusic.yml -g dart-dio-next -o ytmusicapi-dart -c config.json
```
Afterwards, change directory to ytmusicapi-dart and then auto-generate Dart files:
```sh
dart pub run build_runner build
```
Wait a little bit.

Check with `Dart analyzer` if anything wasn't generated. If a few (like 1-3) classes weren't generated, then no problem, just replace those classes with `Object`.

If there are a lot of classes missing, try to regenerate bindings or open an issue.

Afterwards, you have working bindings.

# License
This project is licensed under MIT License.

It's freely available to everyone without any specific restrictions. I also don't restrict how you use bindings and how you license them, but all I want is just a little credit to me - example `Thanks to @mytja for YouTubeOpenAPI` or copyright example `Copyright (c) 2022 mytja`.

Due to MIT restriction, you should include copy of license when building your own project that uses this project.

# Disclaimer
This was strictly made for learning and educational purposes on how to use OpenAPI.
I will not restrict anybody from how are you using this project, just note that [YouTube ToS](https://www.youtube.com/static?template=terms) might.
Please comply with YouTube ToS.

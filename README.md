# Build Grafana docker image
> make build-docker-full

# Push into dockerhub.io
> check docker image name in Makefile which is located on build-docker-full line.  <br>
> docker tag local-image:tagname new-repo:tagname <br>
> docker push new-repo:tagname  <br>

<!-- # docker 설치 방법  -->
<!-- > docker run -d --volume=$(pwd):/ed/ --net=host --name=edgrafana ganadara135/edgrafana:7.1.0-pre-render
> docker run -d --volume=$(pwd):/ed/ --net=host --name=edgrafana  -e "GF_INSTALL_PLUGINS=grafana-image-renderer 1.0.12"  ganadara135/edgrafana:7.1.0-pre -->

<!-- > docker run -d --volume=$(pwd):/ed/ -p 3000:3000 --net=host --name=edgrafana ganadara135/edgrafana:7.1.0-pre -->


<!-- # grafana_reporter 설치
> docker run -d --volume=$(pwd):/pdf/ -p 8686:8686 --net="host" --name pdf izakmarais/grafana-reporter -->

# edgrafan 와 grafana-image-render grafana_reporter 설치
> docker-compose up -d      <br>
 ex) 위 명령어는 DockerCompose 폴더 안에서 실행해도 됨

# grafana_reporter 연결 체크
1. 대시보드 하나 만듦 <br>
2. Apikey 생성 <br>
3. 연결체크 <br>
> curl http://27.96.135.50:8686/api/v5/report/{대시보드uid} <br>
> curl http://27.96.135.50:8686/api/v5/report/4Gs4J46Wk?apitoken=eyJrIjoiTjU5RWhYWGFkWW53SDc2YW9pdmdLZzFWeFhDYlltOWQiLCJuIjoicGRmIiwiaWQiOjF9
4. 참고 pdf reporting link <br>
> https://github.com/IzakMarais/reporter#endpoint <br>


# grafana_plugin 설치
1. docker-compose.yaml 에서 volume 부분에서 plugin 파일과 연결해 줌 <br>
    ex) plugin 파일을 호스트 의 특정 폴더에 넣고, 해당 폴더를 volume 과 연결해줌 <br>


![Grafana](docs/logo-horizontal.png)

The open-source platform for monitoring and observability.

[![License](https://img.shields.io/github/license/grafana/grafana)](LICENSE)
[![Circle CI](https://img.shields.io/circleci/build/gh/grafana/grafana)](https://circleci.com/gh/grafana/grafana)
[![Go Report Card](https://goreportcard.com/badge/github.com/grafana/grafana)](https://goreportcard.com/report/github.com/grafana/grafana)

Grafana allows you to query, visualize, alert on and understand your metrics no matter where they are stored. Create, explore, and share dashboards with your team and foster a data driven culture:

- **Visualize:** Fast and flexible client side graphs with a multitude of options. Panel plugins for many different way to visualize metrics and logs.
- **Dynamic Dashboards:** Create dynamic & reusable dashboards with template variables that appear as dropdowns at the top of the dashboard.
- **Explore Metrics:** Explore your data through ad-hoc queries and dynamic drilldown. Split view and compare different time ranges, queries and data sources side by side.
- **Explore Logs:** Experience the magic of switching from metrics to logs with preserved label filters. Quickly search through all your logs or streaming them live.
- **Alerting:** Visually define alert rules for your most important metrics. Grafana will continuously evaluate and send notifications to systems like Slack, PagerDuty, VictorOps, OpsGenie.
- **Mixed Data Sources:** Mix different data sources in the same graph! You can specify a data source on a per-query basis. This works for even custom datasources.

## Get started

- [Get Grafana](https://grafana.com/get)
- [Installation guides](http://docs.grafana.org/installation/)

Unsure if Grafana is for you? Watch Grafana in action on [play.grafana.org](https://play.grafana.org/)!

## Documentation

The Grafana documentation is available at [grafana.com/docs](https://grafana.com/docs/).

## Contributing

If you're interested in contributing to the Grafana project:

- Start by reading the [Contributing guide](/CONTRIBUTING.md).
- Learn how to set up your local environment, in our [Developer guide](/contribute/developer-guide.md).
- Explore our [beginner-friendly issues](https://github.com/grafana/grafana/issues?q=is%3Aopen+is%3Aissue+label%3A%22beginner+friendly%22).

## Get involved

- Follow [@grafana on Twitter](https://twitter.com/grafana/)
- Read and subscribe to the [Grafana blog](https://grafana.com/blog/)
- If you have a specific question, check out our [discussion forums](https://community.grafana.com/).
- For general discussions, join us on the [official Slack](http://slack.raintank.io/) team.

## License

Grafana is distributed under the [Apache 2.0 License](https://github.com/grafana/grafana/blob/master/LICENSE).

# Running services

As outlined in the [[development environment introduction|DevEnvironment#One-task-to-run-them-all]], all Lagom services defined in a build can be run with a single task: `runAll`. When executing this task, an embedded [[Service Locator|ServiceLocator]] is started, an embedded [[Cassandra server|CassandraServer]] is also started, and then all your services are started, in paralell. Furthermore, all started services will be running in hot-reload mode. Hot-reload means that the services are automatically reloaded on every change you make, so that you don't have to manually restart them.

Most times, the `runAll` task will serve you well. However, there will be occasions when you may want to manually start only a few services, and this is when the `run` task will come in handy. The `run` task is available to each of your Lagom service implementation projects, and you can execute it by simply prefixing the service project's name, i.e., `<your-lagom-project-name>/run`.

One thing you should remember is that `run` only starts the specific service, it doesn't start neither the Service Locator, nor the Cassandra server. Hence, prior to manually starting services, you may want to manually start both the [[Service Locator|ServiceLocator#Start-and-stop]], and the [[Cassandra server|CassandraServer#Start-and-stop]].

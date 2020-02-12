### 🔧 Herramientas

* [Blue Ocean Pipeline Editor](/#development_tools_blue_ocean)
* [Command-line Interface](/#command_line_interface)
* [Command-line Pipeline Linter](/#command_line_pipeline_linter)
* [Replay](/#replay_pipeline)
* [Restart from Stage](/#restart_from_stage)

^^^^^^
<!-- .element: id="development_tools_blue_ocean" -->

#### 🔧 Herramientas: Blue Ocean Pipeline Editor

[Blue Ocean Pipeline Editor 📄](https://jenkins.io/doc/book/blueocean/pipeline-editor/) es una interfaz
gráfica para crear y editar `Pipelines` 

^^^^^^

#### 🔧 Herramientas: Blue Ocean Pipeline Editor

¡Lo mejor es verlo en acción!

^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

Instalar los plugins:

* Blue Ocean
* Config API for Blue Ocean
* Blue Ocean Pipeline Editor


^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

Una vez instalado, dispondremos de un acceso directo en el Dashboard

![blue_ocean_installation_step_1](/slides/images/blue_ocean_installation_step_1.png)

^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

![blue_ocean_installation_step_2](/slides/images/blue_ocean_installation_step_2.png)

^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

Si accedemos al proyecto, veremos el dashboard: 

![blue_ocean_installation_step_3](/slides/images/blue_ocean_installation_step_3.png)

^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

Si accedemos a una ejecución: 

![blue_ocean_installation_step_4](/slides/images/blue_ocean_installation_step_4.png)

^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

También lo podemos utilizar para crear un nuevo pipeline: 

![blue_ocean_new_pipeline_step_1](/slides/images/blue_ocean_new_pipeline_step_1.png)

^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

Vamos a recrear la misma tarea de tipo `Multi-branch Pipeline` que ya tenemos pero utilizando Blue Ocean

![blue_ocean_new_pipeline_step_2](/slides/images/blue_ocean_new_pipeline_step_2.png)

notes:

La URL del repositorio es 
[https://github.com/Be-Core-Code/curso-intro-jenkins-modulo-5-sample-repository-with-jenkinsfile.git](https://github.com/Be-Core-Code/curso-intro-jenkins-modulo-5-sample-repository-with-jenkinsfile.git)

^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

![blue_ocean_new_pipeline_step_3](/slides/images/blue_ocean_new_pipeline_step_3.png)

^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

![blue_ocean_new_pipeline_step_4](/slides/images/blue_ocean_new_pipeline_step_4.png)


^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

Ha sido mucho más rápido y la interfaz es bastante más agradable a la vista...


^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

Además, podemos editar gráficamente los Jenkinfiles:

![blue_ocean_new_pipeline_step_5](/slides/images/blue_ocean_new_pipeline_step_5.png)

^^^^^^

#### 💻️ Práctica: Instalar Blue Ocean Pipeline Editor

Para editar
es necesario dar permiso de escritura sobre el repositorio.

^^^^^^
<!-- .element: id="command_line_interface"-->

#### 🔧 Herramientas: Command-Line Interface (CLI)

Jenkins pone a nuestra disposición un interfaz de comandos para operar sobre Jenkins.

--- 
[Documentación](https://jenkins.io/doc/book/managing/cli/)

^^^^^^
#### 🔧 Herramientas: Command-Line Interface (CLI)

Se puede operar con ella:
* a través de ssh
* utilizando un cliente java

^^^^^^
#### 🔧 Herramientas: Command-Line Interface (CLI)

Para descargarnos el cliente java:

```bash
> wget http://localhost:8080/jnlpJars/jenkins-cli.jar
```

En el siguiente punto veremos un ejemplo de uso.

^^^^^^
#### 🔧 Herramientas: Command-Line Interface (CLI)

¿qué operaciones podemos hacer? Accede a `http://localhost:8080/cli/`

![jenkins_cli_commands](/slides/images/jenkins_cli_commands.png)

^^^^^^

<!-- .element: id="command_line_pipeline_linter"-->

#### 🔧 Herramientas: Command-line Pipeline Linter

[Command-line Pipeline Linter](https://jenkins.io/doc/book/pipeline/development/#linter) es una herramienta
que facilita Jenkins para validar nuestro `Jenkinsfile`.

^^^^^^
#### 🔧 Herramientas: Command-line Pipeline Linter

```bash
> java -jar jenkins-cli.jar -s http://localhost:8080/ -auth admin:admin -webSocket declarative-linter < ./Jenkinsfile
```

^^^^^^
<!-- .element: id="replay_pipeline" -->

#### 🔧 Herramientas: Replay

![pipeline_tools_replay_1](/slides/images/pipeline_tools_replay_1.png)

notes:

Esta funcionalidad está disponible desde dentro de una ejecución de un `Pipeline`

^^^^^^

#### 🔧 Herramientas: Replay

![pipeline_tools_replay_2](/slides/images/pipeline_tools_replay_2.png)

notes:

Podemos volver a lanzar el `Pipeline` cambiando el fichero de definición.

Esto nos permitiría por ejemplo hacer pruebas o depurar un problema antes de
hacer commit de las modificaciones de manera definitiva en el repositorio.

^^^^^^

#### 🔧 Herramientas: Replay

La opción de Replay también está disponible desde la interfaz de Blue Ocean

![pipeline_tools_replay_3](/slides/images/pipeline_tools_replay_3.png)

^^^^^^

#### 🔧 Herramientas: Replay

![pipeline_tools_replay_4](/slides/images/pipeline_tools_replay_4.png)


^^^^^^
<!-- .element: id="restart_from_stage" -->
#### 🔧 Herramientas: Restart from stage

Esta herramienta permite volver a empezar un `Pipeline` desde un paso determinado.

[Documentación](https://jenkins.io/doc/book/pipeline/running-pipelines/#restart-from-a-stage)


^^^^^^
#### 🔧 Herramientas: Restart from stage

Esta funcionalidad está disponible desde dentro de una ejecución de un `Pipeline`

![pipeline_tools_restart_1](/slides/images/pipeline_tools_restart_1.png)

^^^^^^
#### 🔧 Herramientas: Restart from stage

![pipeline_tools_restart_2](/slides/images/pipeline_tools_restart_2.png)

^^^^^^
#### 🔧 Herramientas: Restart from stage

![pipeline_tools_restart_3](/slides/images/pipeline_tools_restart_3.png)

^^^^^^
#### 🔧 Herramientas: Restart from stage

La opción Restart también está disponible desde la interfaz de Blue Ocean

![pipeline_tools_restart_4](/slides/images/pipeline_tools_restart_4.png)

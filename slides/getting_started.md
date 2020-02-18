### Primeros pasos

Forma de crear un `Pipeline`:

* Utilizando la interfaz gráfica de Jenkins
* A través de nuestro repositorio (Jenkinsfile)
* Utilizando el [plugin de Blue Ocean](https://jenkins.io/doc/book/pipeline/getting-started/#through-blue-ocean) (interfaz gráfica)
 
En esta primera sección utilizaremos la interfaz gráfica de Jenkins

^^^^^^

#### Pr^imeros pasos: Crear una tubería

![Creando una tubería: paso 1](/slides/images/classic_ui_pipeline_step_1.png)

^^^^^^

#### Primeros pasos: Crear una tubería

![Creando una tubería: paso 2](/slides/images/classic_ui_pipeline_step_2.png)

notes:

```Jenkinsfile
pipeline {
    agent any 
    stages {
        stage('Paso 1') {
            steps {
                echo '¡Hola desde el primer paso!' 
            }
        }
        stage('Paso 2') {
            steps {
                echo '¡Hola desde el segundo paso!' 
            }
        }
    }
}
```

^^^^^^

#### Primeros pasos: Ejecutar la tubería

Tras ejecutar la tubería vemos: 
![Creando una tubería: paso 3](/slides/images/classic_ui_pipeline_step_3.png)

^^^^^^

#### Primeros pasos: Ejecutar la tubería

 ![Creando una tubería: paso 4](/slides/images/classic_ui_pipeline_step_4.png)

^^^^^^

#### Primeros pasos: Documentación integrada

* ${YOUR_JENKINS_URL}/pipeline-syntax
* A través del enlace que aparece en cualquier tarea de tipo `Pipeline`

![link_to_pipeline_built_in_documentation](/slides/images/link_to_pipeline_built_in_documentation.png)


^^^^^^

#### Primeros pasos: Documentación integrada

El `Snippet Generator` nos ayuda a generar las instrucciones
para incluir dentro de un bloque `step`

![pipeline_built_in_documentation_snippet_generator](/slides/images/pipeline_built_in_documentation_snippet_generator.png)

^^^^^^

#### 💻️ Primeros pasos: snippet generator

Utilizando el `snippet generator` modificar la tubería
que hemos creado para:

* Retrasar la ejecución durante dos segundos
* Ejecuta los dos pasos en paralelo 

notes:

```Jenkinsfile
pipeline {
    agent any 
    stages {
        stage('Paso 1') {
            steps {
                parallel(
                  first: {
                    echo '¡Hola desde el primer paso!' 
                    sleep 2
                  },
                  second: {
                    echo '¡Hola desde el segundo paso!' 
                    sleep 2
                  }
                )
            }
        }
    }
}
```

^^^^^^

#### Primeros pasos: Documentación integrada

Otro elemento importante de la Documentación integrada es _Global Variable Reference_

![pipeline_built_in_documentation_global_variable_reference](/slides/images/pipeline_built_in_documentation_global_variable_reference.png)

notes:

Documentación de las variables que los diferentes plugins
exponen en un `Pipeline` y que podemos utilizar dentro del
`Jenkinsfile`

^^^^^^

#### 💻️ Primeros pasos: Documentación integrada

* Añadir el parámetro NAME al `Pipeline`
* Mostrar en la consola el número de la ejecución junto con el parámetro utilizado

notes:

```Jenkinsfile
pipeline {
    agent any 
    stages {
        stage('Paso 1') {
            steps {
                parallel(
                  first: {
                    echo "${currentBuild.number}: ¡Hola ${params.NAME} desde el primer paso!"
                    sleep 2
                  },
                  second: {
                    echo "${currentBuild.number}: ¡Hola ${params.NAME} desde el segundo paso!"
                    sleep 2
                  }
                )
            }
        }
    }
}
```

^^^^^^

#### Primeros pasos: Documentación integrada

`Declarative Directive Generator` nos ayuda a generar la documentación para las
directivas dentro del bloque `pipeline`, como por ejemplo `agent`, `stage`, `docker`, etc.

^^^^^^

#### Primeros pasos: Documentación integrada

![pipeline_built_in_documentation_declarative_directive_generator](/slides/images/pipeline_built_in_documentation_declarative_directive_generator.png)

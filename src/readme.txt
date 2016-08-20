20160820-01:
环境变量配置：
GRADLE_HOME: D:\ProgramFiles\gradle-2.7
PATH: %GRADLE_HOME%\bin;

查看版本：
gradle -v

First Gradle Task Demo：
task hello {
    doLast {
        println "hello, Gradle!"
    }
}
执行命令：
gradle -q hello

任务依赖：
task intro(dependsOn: hello) << {
    println "I'm Gradle"
}

动态创建任务：
4.times { counter ->
    task "task$counter" << {
        println "I'm task number $counter"
    }
}
执行：
gradle -q task1


API访问：
task hello3 << {
    println "Hello Earth"
}
hello3.doFirst {
    println "hello Venus"
}

hello3.doLast {
    println "hello Mars"
}

hello3 << {
    println "hello Jupiter"
}
执行：
gradle -q hello3


//默认任务
defaultTasks 'clean', 'run'
执行：
gradle -q



20160820-01:
�����������ã�
GRADLE_HOME: D:\ProgramFiles\gradle-2.7
PATH: %GRADLE_HOME%\bin;

�鿴�汾��
gradle -v

First Gradle Task Demo��
task hello {
    doLast {
        println "hello, Gradle!"
    }
}
ִ�����
gradle -q hello

����������
task intro(dependsOn: hello) << {
    println "I'm Gradle"
}

��̬��������
4.times { counter ->
    task "task$counter" << {
        println "I'm task number $counter"
    }
}
ִ�У�
gradle -q task1



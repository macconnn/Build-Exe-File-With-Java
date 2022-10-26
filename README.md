# Build-Exe-File-With-Java
step by step how to  create  exe  with Java project


## Step 1 
Set the Maven in pom.xml

```
<build>
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-compiler-plugin</artifactId>
				<version>2.3.2</version>
				<configuration>
					<encoding>UTF-8</encoding>
					<source>1.8</source>
					<target>1.8</target>
					<showWarnings>true</showWarnings>
					<compilerArguments>
						<extdirs>${project.basedir}/lib</extdirs>
					</compilerArguments>
				</configuration>
			</plugin>
			<plugin>
				<artifactId> maven-assembly-plugin </artifactId>
				<configuration>
					<descriptorRefs>
						<descriptorRef>jar-with-dependencies</descriptorRef>
					</descriptorRefs>
					<archive>
						<manifest>
							<mainClass>ai.nlp.ui.Start</mainClass>
						</manifest>
					</archive>
				</configuration>
				<executions>
					<execution>
						<id>make-assembly</id>
						<phase>package</phase>
						<goals>
							<goal>single</goal>
						</goals>
					</execution>
				</executions>
			</plugin>
		</plugins>
	</build>
```

## Step 2 

After maven update profect , Run as maven install  
in the target folder should has the jar file in dependency  
type this cmd to make sure the jar can work  
```
java -jar XXX.jar
```


## Step 3

Build a folder contain jar jre image(if you  need) using application to create exe i.e. exe4j , jsmooth , launch4j   
important : all files should in the same folder


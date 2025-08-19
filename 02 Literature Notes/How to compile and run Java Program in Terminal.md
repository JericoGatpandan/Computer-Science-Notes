1. Compile the java program, this time explicitly specifying the destination directory as the `classes` directory that you created.
	`javac -d classes src/DataTypes.java`

2. Set the `CLASSPATH` variable.
```shell
export CLASSPATH=$CLASSPATH:/home/project/my_datatypes_proj/classes
```

3. Now when you run the java program, it will run seamlessly as expected.
	`java DataTypes`
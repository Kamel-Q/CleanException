# Android Clean Exception

A Kotlin library to convert the classic StackTrace to a better one and sending its valuable information to a back-end server using Retrofit 2

## Usage

Step 1. Add the JitPack repository to your build file:

### For gradle:
Add it in your root build.gradle at the end of repositories:
~~~

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
  
~~~

### for maven:

~~~

	<repositories>
		<repository>
		    <id>jitpack.io</id>
		    <url>https://jitpack.io</url>
		</repository>
	</repositories>
  
~~~

Step 2. Add the dependecy

### For gradle:

~~~

	dependencies {
	        implementation 'com.github.Kamel-Q:cleanexception:1.0.0'
	}
  
~~~

### For maven:

~~~

	<dependency>
		 <groupId>com.github.Kamel-Q</groupId>
	 	 <artifactId>cleanexception</artifactId>
		 <version>1.0.0</version>
	</dependency>
  
~~~


Step 3. Add permission to the manifest file:

~~~
    	<uses-permission android:name="android.permission.INTERNET" />
~~~

Step 4. Use the library inside your catch clause:


~~~

    catch(ex:Exception){
    
    	CleanException.Init(apiKey,apiSecret,projectKey) // mandatory to link between the client and the server
   	CleanException.setTitle("Example title")
    	CleanException.setDescription("Example description)
    	CleanException.sendExceptionError(ex,this)
	
    }
    
~~~

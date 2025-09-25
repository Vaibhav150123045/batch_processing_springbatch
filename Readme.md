# Batch Processing Project

I had to create a spring initializr which was not present as default in IntelliJ IDEA community.

## Process to do so:
- Download spring initializer zip file (gradle or maven) according to your use case.
- Unzip the file and open it in intelliJ

## I need to know now that how to change project properties like Artifact ID, group ID etc and what is their meaning.
**Answer:** you can change them directly in `pom.xml` (dont change parent properties)

## Next step is to download dependencies and adding them in pom xml.
I was not able to use IntelliJ’s spring initializer so I have to manually add dependencies.  
There are two ways to do so:
1. By updating the `pom.xml` file directly
2. Project Structure → Modules → Dependencies → click +. Select Maven and search for the dependency (e.g., spring-boot-starter-web)

Now after the ‘click +’ process, it is difficult to find the correct dependency from web.  
After getting tired I am trying to add the dependency directly in `pom.xml`.  
Now there is a version mismatch error with parent spring boot version and spring web version.

So the versions were correct, the issue was that the maven local repository was not updated with the remote repository.

### Step 1:
Update local repository:  
`File → Settings → Maven → Repositories → Update`

### Step 2:
Build the project using:  
`./mvnw clean install`

This process ended up removing the version mismatch error but the build was failing.  
Upon looking in depth, got to know that a test case was failing.

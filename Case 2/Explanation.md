CI detected that the dependency upgrade from version **datafaker-1.3.0** to **datafaker-1.4.0** has failed. Here are details to help you understand and fix the problem:
1. Your client utilizes **1** construct which has been modified in the new version of the dependency.
   * <summary>Method <b>between(java.util.Date,java.util.Date)</b> which has been <b>removed</b> in the new version of the dependency</summary>
            
        *  <summary>The failure is identified from the logs generated in the build process. </summary>
          
            *   >[[ERROR] /flink-faker/src/main/java/com/github/knaufk/flink/faker/DateTime.java:[45,40] incompatible types: java.util.Date cannot be converted to java.sql.Timestamp](https://github.com/chains-project/breaking-good/actions/runs/8110103454/job/22166641300#step:4:709)
            *   An error was detected in line 45 which is making use of an outdated API.
             ``` java
             45   super.between(from, to);
            ```
            
        To resolve this issue, there are alternative options available in the new version of the dependency that can replace the incompatible method currently used in the client. You can consider substituting the existing method with one of the following options provided by the new version of the dependency
        ``` java
        Timestamp between(Timestamp,Timestamp);
        ```



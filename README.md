# custom-oidc-discovery


    Copy servlet-1.0-SNAPSHOT.jar to <IS_HOME>/repository/components/lib folder.
    Copy the openid-configuration.json file to <IS_HOME>/repository/conf/identity folder. You can update/modify the values in this file as per your requirement.
    Register the servlet in the <IS_HOME>/repository/conf/tomcat/web.xml file by adding the following elements before the </webapp> element.

    <servlet>
      <servlet-name>Discovery</servlet-name>
      <servlet-class>myPackage.Discovery</servlet-class>
    </servlet>

    <servlet-mapping>
      <servlet-name>Discovery</servlet-name>
      <url-pattern>/oauth2/oidcdiscovery/.well-known/openid-configuration</url-pattern>
    </servlet-mapping>

    Restart the server with updated JSON and execute the following command to obtain the updated discovery data.

    curl -v -k -u admin:admin https://localhost:9443/oauth2/oidcdiscovery/.well-known/openid-configuration


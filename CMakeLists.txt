cmake_minimum_required(VERSION 2.8)
find_package(Java REQUIRED)
include(UseJava)
project(JavaProxyServer)

set(CMAKE_JAVA_COMPILE_FLAGS "-Xlint:deprecation")
set(EXECUTABLE_OUTPUT_PATH ..)

add_jar(JavaProxyServer HttpRequest.java HttpResponse.java ProxyCache.java SCache.java helpers/Util.java)

get_target_property(_jarFile JavaProxyServer JAR_FILE)
get_target_property(_classDir JavaProxyServer CLASSDIR)

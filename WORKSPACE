load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")


rules_kotlin_version = "legacy-1.3.0-rc1"
rules_kotlin_sha = "9de078258235ea48021830b1669bbbb678d7c3bdffd3435f4c0817c921a88e42"
http_archive(
    name = "io_bazel_rules_kotlin",
    urls = ["https://github.com/bazelbuild/rules_kotlin/archive/%s.zip" % rules_kotlin_version],
    type = "zip",
    strip_prefix = "rules_kotlin-%s" % rules_kotlin_version,
    sha256 = rules_kotlin_sha,
)

load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kotlin_repositories", "kt_register_toolchains")
kotlin_repositories()
kt_register_toolchains()

RULES_JVM_EXTERNAL_TAG = "2.7"

RULES_JVM_EXTERNAL_SHA = "f04b1466a00a2845106801e0c5cec96841f49ea4e7d1df88dc8e4bf31523df74"

http_archive(
    name = "rules_jvm_external",
    sha256 = RULES_JVM_EXTERNAL_SHA,
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "com.expedia:graphql-kotlin:1.0.0-RC5",
        "com.expedia:graphql-kotlin-schema-generator:1.0.0-RC5",
        "com.expedia:graphql-kotlin-federation:1.0.0-RC5",
        "com.graphql-java:graphql-java:13.0",
        "org.opentest4j:opentest4j:1.1.1",
        "org.apiguardian:apiguardian-api:1.0.0",
        "org.junit.platform:junit-platform-commons:1.4.2",
        "org.junit.jupiter:junit-jupiter-api:5.4.2",
        "org.junit.jupiter:junit-jupiter-params:5.4.2",
        "org.apache.logging.log4j:log4j-core:2.12.1",
    ],
    repositories = [
        "https://maven-central.storage.googleapis.com/repos/central/data/",
        "https://repo1.maven.org/maven2",
    ],
)

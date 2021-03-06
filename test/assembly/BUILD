#
# Copyright (C) 2020 Grakn Labs
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU Affero General Public License as
# published by the Free Software Foundation, either version 3 of the
# License, or (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Affero General Public License for more details.
#
# You should have received a copy of the GNU Affero General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.
#

load("@graknlabs_dependencies//tool/checkstyle:rules.bzl", "checkstyle_test")

java_test(
    name = "test-daemon",
    srcs = [
        "AssemblyConstants.java",
        "DaemonTest.java",
    ],
    classpath_resources = ["//test/resources:logback-test"],
    data = ["//:assemble-mac-zip"],
    test_class = "grakn.core.test.assembly.DaemonTest",
    deps = [
        "//common",
        "//server",
        "@maven//:commons_io_commons_io",
        "@maven//:org_hamcrest_hamcrest_library",
        "@maven//:org_zeroturnaround_zt_exec",
        "@graknlabs_client_java//:client-java",
    ],
)

java_test(
    name = "test-distribution",
    srcs = [
        "AssemblyConstants.java",
        "DistributionTest.java",
    ],
    classpath_resources = ["//test/resources:logback-test"],
    data = ["//:assemble-mac-zip"],
    test_class = "grakn.core.test.assembly.DistributionTest",
    deps = [
        "//common",
        "@maven//:commons_io_commons_io",
        "@maven//:org_hamcrest_hamcrest_library",
        "@maven//:org_zeroturnaround_zt_exec",
    ],
)

test_suite(
    name = "test-assembly",
    tests = [
        "//test/assembly:test-daemon",
        "//test/assembly:test-distribution",
    ]
)

checkstyle_test(
    name = "checkstyle",
    targets = [
        ":test-daemon",
        ":test-distribution"
    ],
)

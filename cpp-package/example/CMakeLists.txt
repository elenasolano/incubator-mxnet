# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.

# Explicitly set GENERATED property https://gitlab.kitware.com/cmake/cmake/issues/18399
set_property(SOURCE ${CMAKE_CURRENT_LIST_DIR}/../include/mxnet-cpp/op.h PROPERTY GENERATED 1)

if(MSVC)
  add_custom_target(cpp_package_deploy_library ALL
    DEPENDS mxnet
    COMMAND ${CMAKE_COMMAND} -E copy $<TARGET_FILE:mxnet> $<TARGET_FILE_DIR:mlp>)
endif()

set(srcs)
set(include_dirs)

if (CONFIG_OVMS_COMP_SERVER AND CONFIG_OVMS_COMP_SERVER_V2)
  list(APPEND srcs "src/ovms_server_v2.cpp")
  list(APPEND include_dirs "src")
endif ()

# requirements can't depend on config
idf_component_register(SRCS ${srcs}
                       INCLUDE_DIRS ${include_dirs}
                       PRIV_REQUIRES "main"
                       WHOLE_ARCHIVE)

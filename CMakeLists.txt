# Note: Copra's Python bindings use the same CMake options as other projects but we don't need them
AddProject(copra
  GITHUB jrl-umi3218/copra
  GIT_TAG master
  CMAKE_ARGS -DPYTHON_BINDING:BOOL=OFF
  DEPENDS eigen-quadprog
)

AddProject(mc_state_observation
  GITHUB jrl-umi3218/mc_state_observation
  GIT_TAG main
  DEPENDS mc_rtc
)

AddProject(lipm_walking_controller
  GITHUB arntanguy/lipm_walking_controller
  GIT_TAG topic/stabilizer
  DEPENDS copra mc_state_observation
)

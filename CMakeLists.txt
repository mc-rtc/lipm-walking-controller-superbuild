# Note: Copra's Python bindings use the same CMake options as other projects but we don't need them
AddProject(copra
  GITHUB jrl-umi3218/copra
  GIT_TAG origin/master
  CMAKE_ARGS -DPYTHON_BINDING:BOOL=OFF
  DEPENDS eigen-quadprog
)

AddProject(FootSteps_Planner
  GITHUB antodld/FootSteps_Planner
  GIT_TAG origin/main
  DEPENDS mc_rtc
)

AddProject(lipm_walking_controller
  GITHUB mehdi-benallegue/lipm_walking_controller
  GIT_TAG origin/master
  DEPENDS copra mc_state_observation FootSteps_Planner
)

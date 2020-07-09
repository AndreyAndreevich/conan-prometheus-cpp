[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Build Status](https://github.com//AndreyAndreevich/conan-prometheus-cpp/workflows/CI/badge.svg)](https://github.com//AndreyAndreevich/conan-prometheus-cpp/actions)
[![Download](https://api.bintray.com/packages/andrbek/conan/conan-prometheus-cpp%3Aandrbek/images/download.svg)](https://bintray.com/andrbek/conan/conan-prometheus-cpp%3Aandrbek/_latestVersion)

# conan-prometheus-cpp

## Basic setup

    $ conan install . prometheus-cpp/0.9.0@andrbek/stable -o prometheus-cpp:mode=pull
    
## Project setup

If you handle multiple dependencies in your project is better to add a *conanfile.txt*
    
    [requires]
      prometheus-cpp/0.9.0@andrbek/stable

    [options]
      prometheus-cpp:mode=pull                         # REQUIRED, you must specify 'pull' xor 'push'
      prometheus-cpp:shared=False                      # default is False
      prometheus-cpp:enable_compression=True           # default is True
      prometheus-cpp:override_cxx_standard_flags=True  # default is True
      prometheus-cpp:fPIC=True                         # default is True

    [generators]
      cmake

Complete the installation of requirements for your project running:

    conan install .

Project setup installs the library (and all his dependencies) and generates the files *conanbuildinfo.cmake* with all the 
paths and variables that you need to link with your dependencies.

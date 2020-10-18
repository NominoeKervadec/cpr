project('cprcoro', ['c','cpp'], default_options : ['cpp_std=gnu++2a'])

cmake = import('cmake')
cc = meson.get_compiler('cpp')

coro = subproject('cppcoro')
coro_dep = coro.get_variable('cppcoro_dep')
libcurl_dep = dependency('libcurl')

inc = include_directories('include')

src = [
  'cpr/auth.cpp',
  'cpr/cookies.cpp',
  'cpr/cprtypes.cpp',
  'cpr/curl_container.cpp',
  'cpr/curlholder.cpp',
  'cpr/error.cpp',
  'cpr/multipart.cpp',
  'cpr/parameters.cpp',
  'cpr/payload.cpp',
  'cpr/proxies.cpp',
  'cpr/response.cpp',
  'cpr/session.cpp',
  'cpr/timeout.cpp',
  'cpr/unix_socket.cpp',
  'cpr/util.cpp',
]

cprcoro_static = static_library('cprcoro', [src],
                                dependencies: [coro_dep, libcurl_dep],
                                include_directories: [inc],
                                install: true)

cprcoro_dep = declare_dependency(include_directories: [inc],
                                link_with: cprcoro_static)

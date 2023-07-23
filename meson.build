project(
	'chayang',
	'c',
	version: '0.1.0',
	default_options: ['c_std=c11', 'warning_level=2', 'werror=true'],
)

add_project_arguments(
	'-D_POSIX_C_SOURCE=200809L',
	'-Wno-unused-parameter',
	language: 'c',
)

subdir('protocol')

cc = meson.get_compiler('c')

wayland_client = dependency('wayland-client')

executable(
	'chayang',
	['main.c'] + protos_src,
	dependencies: [
		wayland_client,
	],
	include_directories: 'include',
	install: true,
)

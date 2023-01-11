wayland_scanner = dependency('wayland-scanner', native: true, version: '>=1.14.91')
wayland_scanner = find_program(wayland_scanner.get_variable('wayland_scanner'), native: true)

wayland_protocols = dependency('wayland-protocols', version: '>=1.14')
wp_dir = wayland_protocols.get_variable('pkgdatadir')

wayland_scanner_code = generator(
	wayland_scanner,
	output: '@BASENAME@-protocol.c',
	arguments: ['private-code', '@INPUT@', '@OUTPUT@'],
)

wayland_scanner_client = generator(
	wayland_scanner,
	output: '@BASENAME@-protocol.h',
	arguments: ['client-header', '@INPUT@', '@OUTPUT@'],
)

client_protocols = [
	wp_dir / 'stable/viewporter/viewporter.xml',
	wp_dir / 'stable/xdg-shell/xdg-shell.xml',
	wp_dir / 'staging/single-pixel-buffer/single-pixel-buffer-v1.xml',
	'wlr-layer-shell-unstable-v1.xml',
]

protos_src = []
foreach xml : client_protocols
	protos_src += wayland_scanner_code.process(xml)
	protos_src += wayland_scanner_client.process(xml)
endforeach

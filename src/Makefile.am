## Process this file with automake to produce Makefile.in

bin_PROGRAMS = gmameui

BUILT_SOURCES = \
	gmameui-marshaller.c gmameui-marshaller.h

gmameui_SOURCES = \
	common.c common.h \
	gmameui.c gmameui.h \
	gmameui-main-win.c gmameui-main-win.h \
	io.c io.h \
	game_list.h game_list.c \
	rom_entry.h rom_entry.c \
	gmameui-romfix-list.c gmameui-romfix-list.h \
	gmameui-listoutput.c gmameui-listoutput.h \
	gmameui-listoutput-dlg.c gmameui-listoutput-dlg.h \
	gui.c gui.h \
	gmameui-gamelist-view.c gmameui-gamelist-view.h \
	gmameui-sidebar.c gmameui-sidebar.h \
	progression_window.c progression_window.h \
	directories.c directories.h \
	audit.c audit.h \
	gmameui-audit-dlg.c gmameui-audit-dlg.h \
	gmameui-statusbar.c gmameui-statusbar.h \
	gmameui-rominfo-dlg.c gmameui-rominfo-dlg.h \
	gmameui-rommgr-dlg.c gmameui-rommgr-dlg.h \
	gmameui-search-entry.c gmameui-search-entry.h \
	options_string.c options_string.h \
	gtkjoy.c gtkjoy.h \
	gui_prefs.c gui_prefs.h \
	gui_prefs_dialog.c gui_prefs_dialog.h \
	gmameui-zip-utils.c gmameui-zip-utils.h \
	keyboard.c keyboard.h \
	xmame_options.h xmame_options.c \
	mame-exec.h mame-exec.c \
	mame-exec-list.h mame-exec-list.c \
	mame_options.c mame_options.h \
	mame_options_dialog.c mame_options_dialog.h \
	mame_options_legacy.c mame_options_legacy.h \
	mame_options_legacy_dialog.c mame_options_legacy_dialog.h \
	mame_options_dialog_helper.c mame_options_dialog_helper.h \
	cell-renderer-captioned-image.c cell-renderer-captioned-image.h \
	filters_list.c filters_list.h \
	filter.c filter.h \
	gossip-cell-renderer-expander.c gossip-cell-renderer-expander.h \
	$(BUILT_SOURCES)

gmameui-marshaller.h: gmameui-marshallers.list 
	glib-genmarshal --prefix=gmameui_marshaller --header $< > $@

gmameui-marshaller.c: gmameui-marshallers.list 
	echo "#include \"gmameui-marshaller.h\"" > $@ && \
	glib-genmarshal --prefix=gmameui_marshaller --body $< >> $@

gmameui_LDADD = @GTK_LIBS@ $(GLADE2_LIBS) $(VTE_LIBS) $(GNOME_LIBS) $(ARCHIVE_LIBS) $(IMAGEVIEW_LIBS) $(INTLLIBS) -lzip

AM_CPPFLAGS = -g -Wall $(GTK_CFLAGS) $(GLADE2_CFLAGS) \
		$(VTE_CFLAGS) $(GNOME_CFLAGS) \
		-I$(top_srcdir)/include \
		-DDATADIR=\""$(datadir)"\" \
		-DGLADEDIR=\"${datadir}/gmameui/glade/\" \
		-DGMAMEUI_UI_DIR=\"${datadir}/gmameui/ui/\" \
		-DPACKAGE_LOCALE_DIR=\""$(datadir)/locale"\"

ui_DATA = gmameui-ui.xml
uidir = $(datadir)/gmameui/ui/

EXTRA_DIST = $(ui_DATA) gmameui-marshallers.list $(REDUNDANT_FILES)

CLEANFILES = $(BUILT_SOURCES)

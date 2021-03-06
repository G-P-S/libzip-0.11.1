MANFMT=@MANFMT@
man1_MANS=${MAN1:.mdoc=.${MANFMT}}
man3_MANS=${MAN3:.mdoc=.${MANFMT}}

DISTCLEANFILES=${HTML}
EXTRA_DIST=${MANDOC} ${MAN} CMakeLists.txt

MAN1=	zipcmp.mdoc zipmerge.mdoc ziptorrent.mdoc
MAN3=	libzip.mdoc \
	zip_add.mdoc \
	zip_add_dir.mdoc \
	zip_close.mdoc \
	zip_delete.mdoc \
	zip_dir_add.mdoc \
	zip_discard.mdoc \
	zip_error_clear.mdoc \
	zip_error_get.mdoc \
	zip_error_get_sys_type.mdoc \
	zip_error_to_str.mdoc \
	zip_errors.mdoc \
	zip_fclose.mdoc \
	zip_fdopen.mdoc \
	zip_file_add.mdoc \
	zip_file_extra_field_delete.mdoc \
	zip_file_extra_field_get.mdoc \
	zip_file_extra_field_set.mdoc \
	zip_file_extra_fields_count.mdoc \
	zip_file_get_comment.mdoc \
	zip_file_rename.mdoc \
	zip_file_set_comment.mdoc \
	zip_file_strerror.mdoc \
	zip_fopen.mdoc \
	zip_fopen_encrypted.mdoc \
	zip_fread.mdoc \
	zip_get_archive_comment.mdoc \
	zip_get_archive_flag.mdoc \
	zip_get_file_comment.mdoc \
	zip_get_name.mdoc \
	zip_get_num_entries.mdoc \
	zip_get_num_files.mdoc \
	zip_name_locate.mdoc \
	zip_open.mdoc \
	zip_rename.mdoc \
	zip_set_archive_comment.mdoc \
	zip_set_archive_flag.mdoc \
	zip_set_default_password.mdoc \
	zip_set_file_comment.mdoc \
	zip_set_file_compression.mdoc \
	zip_source_buffer.mdoc \
	zip_source_file.mdoc \
	zip_source_filep.mdoc \
	zip_source_free.mdoc \
	zip_source_function.mdoc \
	zip_source_zip.mdoc \
	zip_stat.mdoc \
	zip_stat_init.mdoc \
	zip_unchange.mdoc \
	zip_unchange_all.mdoc \
	zip_unchange_archive.mdoc

install-data-hook: link-man3

LN=ln

link-man3: install-man3 uninstall-hook
	${LN} ${DESTDIR}${man3dir}/zip_error_clear.3 \
		${DESTDIR}${man3dir}/zip_file_error_clear.3
	${LN} ${DESTDIR}${man3dir}/zip_error_get.3 \
		${DESTDIR}${man3dir}/zip_file_error_get.3
	${LN} ${DESTDIR}${man3dir}/zip_file_add.3 \
		${DESTDIR}${man3dir}/zip_file_replace.3
	${LN} ${DESTDIR}${man3dir}/zip_file_extra_field_delete.3 \
		${DESTDIR}${man3dir}/zip_file_extra_field_delete_by_id.3
	${LN} ${DESTDIR}${man3dir}/zip_file_extra_field_get.3 \
		${DESTDIR}${man3dir}/zip_file_extra_field_get_by_id.3
	${LN} ${DESTDIR}${man3dir}/zip_file_extra_fields_count.3 \
		${DESTDIR}${man3dir}/zip_file_extra_fields_count_by_id.3
	${LN} ${DESTDIR}${man3dir}/zip_fopen.3 \
		${DESTDIR}${man3dir}/zip_fopen_index.3
	${LN} ${DESTDIR}${man3dir}/zip_fopen_encrypted.3 \
		${DESTDIR}${man3dir}/zip_fopen_index_encrypted.3
	${LN} ${DESTDIR}${man3dir}/zip_add.3 \
		${DESTDIR}${man3dir}/zip_replace.3
	${LN} ${DESTDIR}${man3dir}/zip_stat.3 \
		${DESTDIR}${man3dir}/zip_stat_index.3
	${LN} ${DESTDIR}${man3dir}/zip_file_strerror.3 \
		${DESTDIR}${man3dir}/zip_strerror.3

uninstall-hook:
	-rm -f ${DESTDIR}${man3dir}/zip_file_error_clear.3
	-rm -f ${DESTDIR}${man3dir}/zip_file_error_get.3
	-rm -f ${DESTDIR}${man3dir}/zip_file_extra_field_delete_by_id.3
	-rm -f ${DESTDIR}${man3dir}/zip_file_extra_field_get_by_id.3
	-rm -f ${DESTDIR}${man3dir}/zip_file_extra_fields_count_by_id.3
	-rm -f ${DESTDIR}${man3dir}/zip_file_replace.3
	-rm -f ${DESTDIR}${man3dir}/zip_fopen_index.3
	-rm -f ${DESTDIR}${man3dir}/zip_fopen_index_encrypted.3
	-rm -f ${DESTDIR}${man3dir}/zip_replace.3
	-rm -f ${DESTDIR}${man3dir}/zip_stat_index.3
	-rm -f ${DESTDIR}${man3dir}/zip_strerror.3

link-html: ${HTML}
	-rm -f zip_file_error_clear.html \
		zip_file_error_get.html \
		zip_file_extra_field_delete_by_id.html \
		zip_file_extra_field_get_by_id.html \
		zip_file_extra_fields_count_by_id.html \
		zip_file_replace.html \
		zip_fopen_index.html \
		zip_fopen_index_encrypted \
		zip_replace.html \
		zip_stat_index.html \
		zip_strerror.html
	${LN} zip_error_clear.html zip_file_error_clear.html
	${LN} zip_error_get.html zip_file_error_get.html
	${LN} zip_file_extra_field_delete.html zip_file_extra_field_delete_by_id.html
	${LN} zip_file_extra_field_get.html zip_file_extra_field_get_by_id.html
	${LN} zip_file_extra_fields_count.html zip_file_extra_fields_count_by_id.html
	${LN} zip_file_add.html zip_file_replace.html
	${LN} zip_fopen.html zip_fopen_index.html
	${LN} zip_fopen_encrypted.html zip_fopen_index_encrypted.html
	${LN} zip_add.html zip_replace.html
	${LN} zip_stat.html zip_stat_index.html
	${LN} zip_file_strerror.html zip_strerror.html

MANDOC=${MAN1} ${MAN3}
HTML=${MANDOC:.mdoc=.html}
MAN=${MANDOC:.mdoc=.man}

MDOC2MAN=mdoc2man
SUFFIXES=.man .mdoc .html

.PHONY: mkman update-errors

mkman: ${MAN}
mkhtml: ${HTML} link-html

mkdocset: mkdocset.pl ${HTML}
	perl mkdocset.pl ${HTML}

update-errors:
	sh $(srcdir)/make_zip_errors.sh $(srcdir)/../lib/zip.h zip_errors.mdoc

.mdoc.man:
#	${MDOC2MAN} $< > $@.$$$$ && mv $@.$$$$ $@

.mdoc.html:
#	mandoc -Thtml -Oman="%N.html",style=../nih-man.css $< > $@.$$$$ && mv $@.$$$$ $@

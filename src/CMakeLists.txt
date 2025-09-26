cmake_minimum_required(VERSION 3.10)
project(CC65 C)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)

include_directories(. ./common)
# Add source files
set(AR65_SOURCES 
	ar65/add.c
	ar65/add.h
	ar65/del.c
	ar65/del.h
	ar65/error.c
	ar65/error.h
	ar65/exports.c
	ar65/exports.h
	ar65/extract.c
	ar65/extract.h
	ar65/fileio.c
	ar65/fileio.h
	ar65/global.c
	ar65/global.h
	ar65/library.c
	ar65/library.h
	ar65/list.c
	ar65/list.h
	ar65/main.c
	ar65/objdata.c
	ar65/objdata.h
	ar65/objfile.c
	ar65/objfile.h
)
set(CA65_SOURCES
	ca65/anonname.c
	ca65/anonname.h
	ca65/asserts.c
	ca65/asserts.h
	ca65/condasm.c
	ca65/condasm.h
	ca65/dbginfo.c
	ca65/dbginfo.h
	ca65/ea.h
	ca65/ea65.c
	ca65/ea65.h
	ca65/easw16.c
	ca65/easw16.h
	ca65/enum.c
	ca65/enum.h
	ca65/error.c
	ca65/error.h
	ca65/expect.c
	ca65/expect.h
	ca65/expr.c
	ca65/expr.h
	ca65/feature.c
	ca65/feature.h
	ca65/filetab.c
	ca65/filetab.h
	ca65/fragment.c
	ca65/fragment.h
	ca65/global.c
	ca65/global.h
	ca65/incpath.c
	ca65/incpath.h
	ca65/instr.c
	ca65/instr.h
	ca65/istack.c
	ca65/istack.h
	ca65/lineinfo.c
	ca65/lineinfo.h
	ca65/listing.c
	ca65/listing.h
	ca65/macro.c
	ca65/macro.h
	ca65/main.c
	ca65/nexttok.c
	ca65/nexttok.h
	ca65/objcode.c
	ca65/objcode.h
	ca65/objfile.c
	ca65/objfile.h
	ca65/options.c
	ca65/options.h
	ca65/pseudo.c
	ca65/pseudo.h
	ca65/repeat.c
	ca65/repeat.h
	ca65/scanner.c
	ca65/scanner.h
	ca65/segdef.c
	ca65/segdef.h
	ca65/segment.c
	ca65/segment.h
	ca65/sizeof.c
	ca65/sizeof.h
	ca65/span.c
	ca65/span.h
	ca65/spool.c
	ca65/spool.h
	ca65/struct.c
	ca65/struct.h
	ca65/studyexpr.c
	ca65/studyexpr.h
	ca65/symbol.c
	ca65/symbol.h
	ca65/symentry.c
	ca65/symentry.h
	ca65/symtab.c
	ca65/symtab.h
	ca65/token.c
	ca65/token.h
	ca65/toklist.c
	ca65/toklist.h
	ca65/ulabel.c
	ca65/ulabel.h
	ca65/)
set(CC65_SOURCES
	cc65/anonname.c
	cc65/anonname.h
	cc65/asmcode.c
	cc65/asmcode.h
	cc65/asmlabel.c
	cc65/asmlabel.h
	cc65/asmstmt.c
	cc65/asmstmt.h
	cc65/assignment.c
	cc65/assignment.h
	cc65/casenode.c
	cc65/casenode.h
	cc65/codeent.c
	cc65/codeent.h
	cc65/codegen.c
	cc65/codegen.h
	cc65/codeinfo.c
	cc65/codeinfo.h
	cc65/codelab.c
	cc65/codelab.h
	cc65/codeopt.c
	cc65/codeopt.h
	cc65/codeoptutil.c
	cc65/codeoptutil.h
	cc65/codeseg.c
	cc65/codeseg.h
	cc65/compile.c
	cc65/compile.h
	cc65/coptadd.c
	cc65/coptadd.h
	cc65/coptbool.c
	cc65/coptbool.h
	cc65/coptc02.c
	cc65/coptc02.h
	cc65/coptcmp.c
	cc65/coptcmp.h
	cc65/coptind.c
	cc65/coptind.h
	cc65/coptjmp.c
	cc65/coptjmp.h
	cc65/coptlong.c
	cc65/coptlong.h
	cc65/coptmisc.c
	cc65/coptmisc.h
	cc65/coptptrload.c
	cc65/coptptrload.h
	cc65/coptptrstore.c
	cc65/coptptrstore.h
	cc65/coptpush.c
	cc65/coptpush.h
	cc65/coptshift.c
	cc65/coptshift.h
	cc65/coptsize.c
	cc65/coptsize.h
	cc65/coptstop.c
	cc65/coptstop.h
	cc65/coptstore.c
	cc65/coptstore.h
	cc65/coptsub.c
	cc65/coptsub.h
	cc65/copttest.c
	cc65/copttest.h
	cc65/coptunary.c
	cc65/coptunary.h
	cc65/copyleft.jrd
	cc65/dataseg.c
	cc65/dataseg.h
	cc65/datatype.c
	cc65/datatype.h
	cc65/declare.c
	cc65/declare.h
	cc65/declattr.c
	cc65/declattr.h
	cc65/error.c
	cc65/error.h
	cc65/expr.c
	cc65/expr.h
	cc65/exprdesc.c
	cc65/exprdesc.h
	cc65/funcdesc.c
	cc65/funcdesc.h
	cc65/function.c
	cc65/function.h
	cc65/global.c
	cc65/global.h
	cc65/goto.c
	cc65/goto.h
	cc65/hexval.c
	cc65/hexval.h
	cc65/ident.c
	cc65/ident.h
	cc65/incpath.c
	cc65/incpath.h
	cc65/initdata.c
	cc65/initdata.h
	cc65/input.c
	cc65/input.h
	cc65/lineinfo.c
	cc65/lineinfo.h
	cc65/litpool.c
	cc65/litpool.h
	cc65/loadexpr.c
	cc65/loadexpr.h
	cc65/locals.c
	cc65/locals.h
	cc65/loop.c
	cc65/loop.h
	cc65/macrotab.c
	cc65/macrotab.h
	cc65/main.c
	cc65/opcodes.c
	cc65/opcodes.h
	cc65/output.c
	cc65/output.h
	cc65/ppexpr.c
	cc65/ppexpr.h
	cc65/pragma.c
	cc65/pragma.h
	cc65/preproc.c
	cc65/preproc.h
	cc65/reginfo.c
	cc65/reginfo.h
	cc65/scanner.c
	cc65/scanner.h
	cc65/scanstrbuf.c
	cc65/scanstrbuf.h
	cc65/segments.c
	cc65/segments.h
	cc65/seqpoint.c
	cc65/seqpoint.h
	cc65/shiftexpr.c
	cc65/shiftexpr.h
	cc65/stackptr.c
	cc65/stackptr.h
	cc65/standard.c
	cc65/standard.h
	cc65/staticassert.c
	cc65/staticassert.h
	cc65/stdfunc.c
	cc65/stdfunc.h
	cc65/stdnames.c
	cc65/stdnames.h
	cc65/stmt.c
	cc65/stmt.h
	cc65/swstmt.c
	cc65/swstmt.h
	cc65/symentry.c
	cc65/symentry.h
	cc65/symtab.c
	cc65/symtab.h
	cc65/testexpr.c
	cc65/testexpr.h
	cc65/textseg.c
	cc65/textseg.h
	cc65/typecmp.c
	cc65/typecmp.h
	cc65/typeconv.c
	cc65/typeconv.h
	cc65/util.c
	cc65/util.h
	cc65/wrappedcall.c
	cc65/wrappedcall.h
)
set(CHRCVT65_SOURCES
	chrcvt65/main.c
	chrcvt65/error.h
	chrcvt65/error.c
)
set(CL65_SOURCES
	cl65/error.c
	cl65/error.h
	cl65/global.c
	cl65/global.h
	cl65/main.c
	cl65/spawn-amiga.inc
	cl65/spawn-unix.inc
)
set(CO65_SOURCES
	co65/convert.c
	co65/convert.h
	co65/error.c
	co65/error.h
	co65/fileio.c
	co65/fileio.h
	co65/global.c
	co65/global.h
	co65/main.c
	co65/model.c
	co65/model.h
	co65/o65.c
	co65/o65.h
)
set(COMMON_SOURCES
	common/abend.c
	common/abend.h
	common/addrsize.c
	common/addrsize.h
	common/alignment.c
	common/alignment.h
	common/assertion.c
	common/assertion.h
	common/attrib.h
	common/bitops.c
	common/bitops.h
	common/capability.c
	common/capability.h
	common/cddefs.h
	common/chartype.c
	common/chartype.h
	common/check.c
	common/check.h
	common/cmdline.c
	common/cmdline.h
	common/coll.c
	common/coll.h
	common/consprop.c
	common/consprop.h
	common/cpu.c
	common/cpu.h
	common/debugflag.c
	common/debugflag.h
	common/exprdefs.c
	common/exprdefs.h
	common/fileid.c
	common/fileid.h
	common/filepos.c
	common/filepos.h
	common/filestat.c
	common/filestat.h
	common/filetime.c
	common/filetime.h
	common/filetype.c
	common/filetype.h
	common/fname.c
	common/fname.h
	common/fp.c
	common/fp.h
	common/fragdefs.h
	common/gentype.c
	common/gentype.h
	common/hashfunc.c
	common/hashfunc.h
	common/hashtab.c
	common/hashtab.h
	common/hlldbgsym.h
	common/intptrstack.c
	common/intptrstack.h
	common/intstack.c
	common/intstack.h
	common/libdefs.h
	common/lidefs.h
	common/matchpat.c
	common/matchpat.h
	common/mmodel.c
	common/mmodel.h
	common/objdefs.h
	common/optdefs.h
	common/print.c
	common/print.h
	common/scopedefs.h
	common/searchpath.c
	common/searchpath.h
	common/segdefs.h
	common/segnames.c
	common/segnames.h
	common/shift.c
	common/shift.h
	common/strbuf.c
	common/strbuf.h
	common/strpool.c
	common/strpool.h
	common/strstack.c
	common/strstack.h
	common/strutil.c
	common/strutil.h
	common/symdefs.h
	common/target.c
	common/target.h
	common/tgttrans.c
	common/tgttrans.h
	common/va_copy.h
	common/version.c
	common/version.h
	common/xmalloc.c
	common/xmalloc.h
	common/xsprintf.c
	common/xsprintf.h
)
set(DA65_SOURCES
	da65/asminc.c
	da65/asminc.h
	da65/attrtab.c
	da65/attrtab.h
	da65/code.c
	da65/code.h
	da65/comments.c
	da65/comments.h
	da65/data.c
	da65/data.h
	da65/error.c
	da65/error.h
	da65/global.c
	da65/global.h
	da65/handler.c
	da65/handler.h
	da65/infofile.c
	da65/infofile.h
	da65/labels.c
	da65/labels.h
	da65/main.c
	da65/opc4510.c
	da65/opc4510.h
	da65/opc45GS02.c
	da65/opc45GS02.h
	da65/opc6502.c
	da65/opc6502.h
	da65/opc6502dtv.c
	da65/opc6502dtv.h
	da65/opc6502x.c
	da65/opc6502x.h
	da65/opc65816.c
	da65/opc65816.h
	da65/opc65c02.c
	da65/opc65c02.h
	da65/opc65ce02.c
	da65/opc65ce02.h
	da65/opc65sc02.c
	da65/opc65sc02.h
	da65/opcdesc.h
	da65/opchuc6280.c
	da65/opchuc6280.h
	da65/opcm740.c
	da65/opcm740.h
	da65/opctable.c
	da65/opctable.h
	da65/opcw65c02.c
	da65/opcw65c02.h
	da65/output.c
	da65/output.h
	da65/scanner.c
	da65/scanner.h
	da65/segment.c
	da65/segment.h
)
set(DBGINFO_SOURCES
	dbginfo/dbginfo.c
	dbginfo/dbginfo.h
	dbginfo/dbgsh.c
)
set(GRC65_SOURCES
	grc65/main.c
)
set(LD65_SOURCES
	ld65/asserts.c
	ld65/asserts.h
	ld65/bin.c
	ld65/bin.h
	ld65/binfmt.c
	ld65/binfmt.h
	ld65/cfgexpr.c
	ld65/cfgexpr.h
	ld65/condes.c
	ld65/condes.h
	ld65/config.c
	ld65/config.h
	ld65/dbgfile.c
	ld65/dbgfile.h
	ld65/dbgsyms.c
	ld65/dbgsyms.h
	ld65/error.c
	ld65/error.h
	ld65/exports.c
	ld65/exports.h
	ld65/expr.c
	ld65/expr.h
	ld65/extsyms.c
	ld65/extsyms.h
	ld65/fileinfo.c
	ld65/fileinfo.h
	ld65/fileio.c
	ld65/fileio.h
	ld65/filepath.c
	ld65/filepath.h
	ld65/fragment.c
	ld65/fragment.h
	ld65/global.c
	ld65/global.h
	ld65/library.c
	ld65/library.h
	ld65/lineinfo.c
	ld65/lineinfo.h
	ld65/main.c
	ld65/mapfile.c
	ld65/mapfile.h
	ld65/memarea.c
	ld65/memarea.h
	ld65/o65.c
	ld65/o65.h
	ld65/objdata.c
	ld65/objdata.h
	ld65/objfile.c
	ld65/objfile.h
	ld65/scanner.c
	ld65/scanner.h
	ld65/scopes.c
	ld65/scopes.h
	ld65/segments.c
	ld65/segments.h
	ld65/span.c
	ld65/span.h
	ld65/spool.c
	ld65/spool.h
	ld65/tpool.c
	ld65/tpool.h
	ld65/xex.c
	ld65/xex.h
)
set(OD65_SOURCES
	od65/dump.c
	od65/dump.h
	od65/error.c
	od65/error.h
	od65/fileio.c
	od65/fileio.h
	od65/global.c
	od65/global.h
	od65/main.c
)
set(SIM65_SOURCES
	sim65/6502.c
	sim65/6502.h
	sim65/error.c
	sim65/error.h
	sim65/main.c
	sim65/memory.c
	sim65/memory.h
	sim65/paravirt.c
	sim65/paravirt.h
	sim65/peripherals.c
	sim65/peripherals.h
	sim65/trace.c
	sim65/trace.h
)
set(SP65_SOURCES
	sp65/asm.c
	sp65/asm.h
	sp65/attr.c
	sp65/attr.h
	sp65/bin.c
	sp65/bin.h
	sp65/bitmap.c
	sp65/bitmap.h
	sp65/c.c
	sp65/c.h
	sp65/color.c
	sp65/color.h
	sp65/convert.c
	sp65/convert.h
	sp65/error.c
	sp65/error.h
	sp65/fileio.c
	sp65/fileio.h
	sp65/geosbitmap.c
	sp65/geosbitmap.h
	sp65/geosicon.c
	sp65/geosicon.h
	sp65/input.c
	sp65/input.h
	sp65/koala.c
	sp65/koala.h
	sp65/lynxpalette.c
	sp65/lynxpalette.h
	sp65/lynxsprite.c
	sp65/lynxsprite.h
	sp65/main.c
	sp65/output.c
	sp65/output.h
	sp65/palconv.c
	sp65/palconv.h
	sp65/palette.c
	sp65/palette.h
	sp65/pcx.c
	sp65/pcx.h
	sp65/pixel.h
	sp65/raw.c
	sp65/raw.h
	sp65/vic2sprite.c
	sp65/vic2sprite.h
)

add_library(common STATIC ${COMMON_SOURCES})

add_executable(ar65 ${AR65_SOURCES})
add_executable(ca65 ${CA65_SOURCES})
add_executable(cc65 ${CC65_SOURCES})
add_executable(chrcvt65 ${CHRCVT65_SOURCES})
add_executable(cl65 ${CL65_SOURCES})
add_executable(co65 ${CO65_SOURCES})
add_executable(dbginfo ${DBGINFO_SOURCES})
add_executable(da65 ${CO65_SOURCES})
add_executable(grc65 ${GRC65_SOURCES})
add_executable(ld65 ${LD65_SOURCES})
add_executable(od65 ${OD65_SOURCES})
add_executable(sim65 ${SIM65_SOURCES})
add_executable(sp65 ${SP65_SOURCES})

if(MSVC)
	target_compile_options(common PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(ar65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(ca65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(cc65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(chrcvt65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(cl65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(co65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(da65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(dbginfo PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(grc65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(ld65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(od65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(sim65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(sp65 PRIVATE -D_CRT_SECURE_NO_WARNINGS)
endif()


set_target_properties(ar65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(ca65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(cc65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(chrcvt65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(cl65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(co65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(da65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(dbginfo PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(grc65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(ld65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(od65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(sim65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(sp65 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)

target_link_libraries(ar65 PRIVATE common)
target_link_libraries(ca65 PRIVATE common)
target_link_libraries(cc65 PRIVATE common)
include(CheckLibraryExists)
check_library_exists(m ceil "" MATH_FOUND)
if(MATH_FOUND)
    target_link_libraries(cc65 m)
endif()
target_link_libraries(chrcvt65 PRIVATE common)
target_link_libraries(cl65 PRIVATE common)
target_link_libraries(co65 PRIVATE common)
target_link_libraries(da65 PRIVATE common)
target_link_libraries(dbginfo PRIVATE common)
target_link_libraries(grc65 PRIVATE common)
target_link_libraries(ld65 PRIVATE common)
target_link_libraries(od65 PRIVATE common)
target_link_libraries(sim65 PRIVATE common)
target_link_libraries(sp65 PRIVATE common)



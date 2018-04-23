cmake_minimum_required(VERSION 3.4.1)

add_library(LineBreak-v2 SHARED     src/main/cpp/LineBreak/LineBreaker.cpp
                                    src/main/cpp/LineBreak/liblinebreak-2.0/linebreak.c
                                    src/main/cpp/LineBreak/liblinebreak-2.0/linebreakdata.c
                                    src/main/cpp/LineBreak/liblinebreak-2.0/linebreakdef.c)

add_library(DeflatingDecompressor-v3 SHARED  src/main/cpp/DeflatingDecompressor/DeflatingDecompressor.cpp)

add_library(expat  src/main/cpp/expat-2.0.1/lib/xmlparse.c
                         src/main/cpp/expat-2.0.1/lib/xmlrole.c
                         src/main/cpp/expat-2.0.1/lib/xmltok.c)
add_definitions(-DHAVE_EXPAT_CONFIG_H)
include_directories(src/main/cpp/expat-2.0.1 src/main/cpp/expat-2.0.1/lib)
link_directories(src/main/cpp/expat-2.0.1/lib)

#target_include_directories(NativeFormats-v4 src/main/cpp/expat-2.0.1/lib)
#link_libraries(expat)

install(TARGETS expat ARCHIVE DESTINATION	src/main/cpp/NativeFormats)
add_library(NativeFormats-v4 SHARED  src/main/cpp/NativeFormats/JavaNativeFormatPlugin.cpp
                                        src/main/cpp/NativeFormats/JavaPluginCollection.cpp
                                        src/main/cpp/NativeFormats/main.cpp
                                        src/main/cpp/NativeFormats/util/AndroidUtil.cpp
                                        src/main/cpp/NativeFormats/util/JniEnvelope.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/constants/ZLXMLNamespace.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/drm/FileEncryptionInfo.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/encoding/DummyEncodingConverter.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/encoding/Utf16EncodingConverters.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/encoding/Utf8EncodingConverter.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/encoding/JavaEncodingConverter.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/encoding/ZLEncodingCollection.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/encoding/ZLEncodingConverter.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/filesystem/ZLDir.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/filesystem/ZLFSManager.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/filesystem/ZLFile.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/filesystem/ZLInputStreamDecorator.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/filesystem/zip/ZLGzipInputStream.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/filesystem/zip/ZLZDecompressor.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/filesystem/zip/ZLZipDir.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/filesystem/zip/ZLZipEntryCache.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/filesystem/zip/ZLZipHeader.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/filesystem/zip/ZLZipInputStream.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/language/ZLCharSequence.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/language/ZLLanguageDetector.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/language/ZLLanguageList.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/language/ZLLanguageMatcher.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/language/ZLStatistics.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/language/ZLStatisticsGenerator.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/language/ZLStatisticsItem.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/language/ZLStatisticsXMLReader.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/library/ZLibrary.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/logger/ZLLogger.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/util/ZLFileUtil.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/util/ZLLanguageUtil.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/util/ZLStringUtil.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/util/ZLUnicodeUtil.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/xml/ZLAsynchronousInputStream.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/xml/ZLPlainAsynchronousInputStream.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/xml/ZLXMLReader.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/xml/expat/ZLXMLReaderInternal.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/unix/filesystem/ZLUnixFSDir.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/unix/filesystem/ZLUnixFSManager.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/unix/filesystem/ZLUnixFileInputStream.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/unix/filesystem/ZLUnixFileOutputStream.cpp
                                        src/main/cpp/NativeFormats/zlibrary/core/src/unix/library/ZLUnixLibrary.cpp
                                        src/main/cpp/NativeFormats/zlibrary/text/src/model/ZLCachedMemoryAllocator.cpp
                                        src/main/cpp/NativeFormats/zlibrary/text/src/model/ZLTextModel.cpp
                                        src/main/cpp/NativeFormats/zlibrary/text/src/model/ZLTextParagraph.cpp
                                        src/main/cpp/NativeFormats/zlibrary/text/src/model/ZLTextStyleEntry.cpp
                                        src/main/cpp/NativeFormats/zlibrary/text/src/model/ZLVideoEntry.cpp
                                        src/main/cpp/NativeFormats/zlibrary/text/src/fonts/FontManager.cpp
                                        src/main/cpp/NativeFormats/zlibrary/text/src/fonts/FontMap.cpp
                                        src/main/cpp/NativeFormats/zlibrary/ui/src/android/filesystem/JavaFSDir.cpp
                                        src/main/cpp/NativeFormats/zlibrary/ui/src/android/filesystem/JavaInputStream.cpp
                                        src/main/cpp/NativeFormats/zlibrary/ui/src/android/filesystem/ZLAndroidFSManager.cpp
                                        src/main/cpp/NativeFormats/zlibrary/ui/src/android/library/ZLAndroidLibraryImplementation.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/bookmodel/BookModel.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/bookmodel/BookReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/EncodedTextReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/FormatPlugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/PluginCollection.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/fb2/FB2BookReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/fb2/FB2CoverReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/fb2/FB2MetaInfoReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/fb2/FB2Plugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/fb2/FB2Reader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/fb2/FB2TagManager.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/fb2/FB2UidReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/css/CSSInputStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/css/CSSSelector.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/css/StringInputStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/css/StyleSheetParser.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/css/StyleSheetTable.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/css/StyleSheetUtil.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/html/HtmlBookReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/html/HtmlDescriptionReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/html/HtmlEntityCollection.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/html/HtmlPlugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/html/HtmlReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/html/HtmlReaderStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/NCXReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/OEBBookReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/OEBCoverReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/OEBEncryptionReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/OEBMetaInfoReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/OEBPlugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/OEBSimpleIdReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/OEBTextStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/OEBUidReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/OPFReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/oeb/XHTMLImageFinder.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/BitReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/DocDecompressor.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/HtmlMetainfoReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/HuffDecompressor.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/MobipocketHtmlBookReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/MobipocketPlugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/PalmDocLikePlugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/PalmDocLikeStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/PalmDocStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/PdbPlugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/PdbReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/PdbStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/pdb/SimplePdbPlugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/rtf/RtfBookReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/rtf/RtfDescriptionReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/rtf/RtfPlugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/rtf/RtfReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/rtf/RtfReaderStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/txt/PlainTextFormat.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/txt/TxtBookReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/txt/TxtPlugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/txt/TxtReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/util/EntityFilesCollector.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/util/MergedStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/util/MiscUtil.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/util/XMLTextStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/xhtml/XHTMLReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/xhtml/XHTMLTagInfo.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/DocBookReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/DocMetaInfoReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/DocPlugin.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/DocStreams.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/OleMainStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/OleStorage.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/OleStream.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/OleStreamParser.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/OleStreamReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/OleUtil.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/DocInlineImageReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/DocFloatImageReader.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/formats/doc/DocAnsiConverter.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/library/Author.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/library/Book.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/library/Comparators.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/library/Tag.cpp
                                        src/main/cpp/NativeFormats/fbreader/src/library/UID.cpp)
add_definitions(-Wall)
include_directories( src/main/cpp/NativeFormats/util
                             src/main/cpp/NativeFormats/zlibrary/core/src/constants
                             src/main/cpp/NativeFormats/zlibrary/core/src/drm
                             src/main/cpp/NativeFormats/zlibrary/core/src/encoding
                             src/main/cpp/NativeFormats/zlibrary/core/src/filesystem
                             src/main/cpp/NativeFormats/zlibrary/core/src/image
                             src/main/cpp/NativeFormats/zlibrary/core/src/language
                             src/main/cpp/NativeFormats/zlibrary/core/src/library
                             src/main/cpp/NativeFormats/zlibrary/core/src/logger
                             src/main/cpp/NativeFormats/zlibrary/core/src/util
                             src/main/cpp/NativeFormats/zlibrary/core/src/xml
                             src/main/cpp/NativeFormats/zlibrary/text/src/model
                             src/main/cpp/NativeFormats/zlibrary/text/src/fonts)
#add_dependencies(NativeFormats-v4 expat)
message(====================================================================================)
#target_link_libraries(NativeFormats-v4 expat)
find_library(log-lib  log )
find_library(z-lib z)

target_link_libraries(LineBreak-v2  ${log-lib} )
target_link_libraries(DeflatingDecompressor-v3  ${log-lib}  ${z-lib})
target_link_libraries(NativeFormats-v4 ${log-lib} ${z-lib} expat)

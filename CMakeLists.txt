cmake_minimum_required(VERSION 4.0)

project(Minikin)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_library(Minikin)
target_sources(Minikin
	PRIVATE
		libs/minikin/BidiUtils.cpp
		libs/minikin/CmapCoverage.cpp
		libs/minikin/Debug.cpp
		libs/minikin/Emoji.cpp
		libs/minikin/Font.cpp
		libs/minikin/FontCollection.cpp
		libs/minikin/FontFamily.cpp
		libs/minikin/FontFeatureUtils.cpp
		libs/minikin/FontFileParser.cpp
		libs/minikin/FontUtils.cpp
		libs/minikin/GraphemeBreak.cpp
		libs/minikin/GreedyLineBreaker.cpp
		libs/minikin/Hyphenator.cpp
		libs/minikin/HyphenatorMap.cpp
		libs/minikin/Layout.cpp
		libs/minikin/LayoutCore.cpp
		libs/minikin/LayoutUtils.cpp
		libs/minikin/LineBreaker.cpp
		libs/minikin/LineBreakerUtil.cpp
		libs/minikin/Locale.cpp
		libs/minikin/LocaleListCache.cpp
		libs/minikin/MeasuredText.cpp
		libs/minikin/Measurement.cpp
		libs/minikin/MinikinFontFactory.cpp
		libs/minikin/MinikinInternal.cpp
		libs/minikin/OptimalLineBreaker.cpp
		libs/minikin/ScriptUtils.cpp
		libs/minikin/SparseBitSet.cpp
		libs/minikin/SystemFonts.cpp
		libs/minikin/WordBreaker.cpp
	PUBLIC
		FILE_SET HEADERS
		BASE_DIRS include
)

find_package(ICU COMPONENTS uc REQUIRED)
target_include_directories(Minikin
	PRIVATE
		include
		${HARFBUZZ_INCLUDE_DIR}
)
target_link_libraries(Minikin
	PRIVATE
		ICU::uc
		${HARFBUZZ_LIBRARY_DIR}/libharfbuzz.a
)
CMAKE_MINIMUM_REQUIRED(VERSION 2.8.7)

SET(CMAKE_INCLUDE_CURRENT_DIR 1)

PROJECT(libcds)

include_directories(include)

add_subdirectory(tests)

SET(cds_SRCS
	src/static/bitsequence/BitSequence.cpp
	src/static/bitsequence/BitSequenceBuilderDArray.cpp
	src/static/bitsequence/BitSequenceBuilderRG.cpp
	src/static/bitsequence/BitSequenceBuilderRRR.cpp
	src/static/bitsequence/BitSequenceBuilderSDArray.cpp
	src/static/bitsequence/BitSequenceDArray.cpp
	src/static/bitsequence/BitSequenceRG.cpp
	src/static/bitsequence/BitSequenceRRR.cpp
	src/static/bitsequence/BitSequenceSDArray.cpp
	src/static/bitsequence/sdarraySadakane.cpp
	src/static/bitsequence/TableOffsetRRR.cpp
	src/static/coders/huff.cpp
	src/static/coders/HuffmanCoder.cpp
	src/static/mapper/Makefile
	src/static/mapper/Mapper.cpp
	src/static/mapper/MapperCont.cpp
	src/static/mapper/MapperNone.cpp
	src/static/mapper/MapperRev.cpp
	src/static/permutation/perm.cpp
	src/static/permutation/Permutation.cpp
	src/static/permutation/PermutationBuilderMRRR.cpp
	src/static/permutation/PermutationBuilderWT.cpp
	src/static/permutation/PermutationMRRR.cpp
	src/static/permutation/PermutationWT.cpp
	src/static/sequence/BitmapsSequence.cpp
	src/static/sequence/Sequence.cpp
	src/static/sequence/SequenceAlphPart.cpp
	src/static/sequence/SequenceBuilderAlphPart.cpp
	src/static/sequence/SequenceBuilderGMR.cpp
	src/static/sequence/SequenceBuilderGMRChunk.cpp
	src/static/sequence/SequenceBuilderStr.cpp
	src/static/sequence/SequenceBuilderWaveletMatrix.cpp
	src/static/sequence/SequenceBuilderWaveletTree.cpp
	src/static/sequence/SequenceBuilderWaveletTreeNoptrs.cpp
	src/static/sequence/SequenceBuilderWaveletTreeNoptrsS.cpp
	src/static/sequence/SequenceGMR.cpp
	src/static/sequence/SequenceGMRChunk.cpp
	src/static/sequence/WaveletMatrix.cpp
	src/static/sequence/WaveletTree.cpp
	src/static/sequence/WaveletTreeNoptrs.cpp
	src/static/sequence/WaveletTreeNoptrsS.cpp
	src/static/sequence/wt_coder.cpp
	src/static/sequence/wt_coder_binary.cpp
	src/static/sequence/wt_coder_huff.cpp
	src/static/sequence/wt_node.cpp
	src/static/sequence/wt_node_internal.cpp
	src/static/sequence/wt_node_leaf.cpp
	src/static/suffixtree/factorization.cpp
	src/static/suffixtree/factorization_var.cpp
	src/static/suffixtree/LCP.cpp
	src/static/suffixtree/LCP_DAC.cpp
	src/static/suffixtree/LCP_DAC_VAR.cpp
	src/static/suffixtree/LCP_FMN.cpp
	src/static/suffixtree/LCP_naive.cpp
	src/static/suffixtree/LCP_PhiSpare.cpp
	src/static/suffixtree/LCP_PT.cpp
	src/static/suffixtree/LCP_Sad.cpp
	src/static/suffixtree/NPR.cpp
	src/static/suffixtree/NPR_CN.cpp
	src/static/suffixtree/NPR_FMN.cpp
	src/static/suffixtree/NSV.cpp
	src/static/suffixtree/PSV.cpp
	src/static/suffixtree/RMQ_succinct.cpp
	src/static/suffixtree/RMQ_succinct_lcp.cpp
	src/static/suffixtree/SuffixTree.cpp
	src/static/suffixtree/SuffixTreeY.cpp
	src/static/textindex/comparray4.cpp
	src/static/textindex/mmap.cpp
	src/static/textindex/qsufsort.cpp
	src/static/textindex/suftest3.test.cpp
	src/static/textindex/TextIndex.cpp
	src/static/textindex/TextIndexCSA.cpp
	src/utils/Array.cpp
	src/utils/BitString.cpp
	src/utils/cppUtils.cpp
	src/utils/timing.cpp
	)

ADD_LIBRARY(cds ${cds_SRCS})
INSTALL(TARGETS cds DESTINATION lib)
#INSTALL(FILES cds.pc DESTINATION lib)
########### install files ###############


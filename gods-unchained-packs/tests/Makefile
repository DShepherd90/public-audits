.PHONY: test

SOLC_FLAGS=--bin --abi
OPT=--optimize --optimize-runs 10000
BUILD_DIR=build

SOURCE_DIR=../code/contracts/
LEVEL_DIR=**/
#OTHERS_DIR=../../code//solidity/contracts/interfaces/
#TEST_SOURCE_DIR=../contracts/


# Dangerous, but useful for testing known contracts
ALLOWED_PATHS=/

SOLIDITY_CONTRACTS=*.sol

all: clean compile

clean:
	mkdir -p ${BUILD_DIR}
#	rm -rf ${BUILD_DIR}/*

compile: $(SOLIDITY_CONTRACTS)

$(SOLIDITY_CONTRACTS):
	solc -o ${BUILD_DIR} --overwrite ${OPT} --allow-paths . ${SOLC_FLAGS}  ${SOURCE_DIR}$@
	solc -o ${BUILD_DIR} --overwrite ${OPT} --allow-paths . ${SOLC_FLAGS}  ${SOURCE_DIR}${LEVEL_DIR}$@
	solc -o ${BUILD_DIR} --overwrite ${OPT} --allow-paths . ${SOLC_FLAGS}  ${SOURCE_DIR}${LEVEL_DIR}${LEVEL_DIR}$@
#	cd node_modules; solc -o ${BUILD_DIR} --overwrite ${OPT} --allow-paths . ${SOLC_FLAGS}  ${OTHERS_DIR}$@
#	solc -o ${BUILD_DIR} --overwrite ${OPT} --allow-paths ${ALLOWED_PATHS} sources=${SOURCE_DIR} ${SOLC_FLAGS} ${TEST_SOURCE_DIR}$@

build-makefile: ENV_VARS
	@mkdir -p build-makefile && rm -rf build && ln -s build-makefile build
	@rm -rf ipks hover.version

	@echo "=============================================="
	@echo "[1/2] Generate Makefiles                      "
	@echo "=============================================="
	@echo ""
	@cd build && cmake -Wno-deprecated ${CMAKE_LAUNCHER_CCACHE} -G "CodeBlocks - Unix Makefiles" ${HOVER_REPO_ROOT}

	@echo ""
	@echo "=============================================="
	@echo "[2/2] Build and install                       "
	@echo "=============================================="
	@echo ""
	@cd build && make -j${MAKE_J_NUMBER} -s --no-print-directory
	@cd build && make install-all/fast -s --no-print-directory && make install-post/fast
	@./adsp_signed.sh

all:
	@mkdir -p build
	
	@echo "=============================================="
	@echo "[1/2] Generate Makefiles                      "
	@echo "=============================================="
	@echo ""
	@cd build && cmake ..

	@echo ""
	@echo "=============================================="
	@echo "[2/2] Build and install                       "
	@echo "=============================================="
	@echo ""
	@cd build && make




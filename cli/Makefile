LIGHTNING_CLI_SRC := cli/lightning-cli.c
LIGHTNING_CLI_OBJS := $(LIGHTNING_CLI_SRC:.c=.o)

ALL_C_SOURCES += $(LIGHTNING_CLI_SRC)
ALL_C_HEADERS +=
ALL_PROGRAMS += cli/lightning-cli

LIGHTNING_CLI_COMMON_OBJS :=			\
	bitcoin/chainparams.o			\
	common/configdir.o			\
	common/configvar.o			\
	common/json_parse_simple.o		\
	common/status_levels.o			\
	common/utils.o				\
	common/version.o

$(LIGHTNING_CLI_OBJS): $(JSMN_HEADERS) $(COMMON_HEADERS) $(CCAN_HEADERS)

cli/lightning-cli: $(LIGHTNING_CLI_OBJS) $(LIGHTNING_CLI_COMMON_OBJS) $(JSMN_OBJS) libccan.a

include cli/test/Makefile

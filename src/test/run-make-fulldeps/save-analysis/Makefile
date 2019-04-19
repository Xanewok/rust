-include ../tools.mk
all: code
krate2: krate2.rs
	$(RUSTC) $<
code: foo.rs krate2
	$(RUSTC) foo.rs -Zsave-analysis
	# Don't panic on malformed config (uses default instead)
	RUST_SAVE_ANALYSIS_CONFIG="{" $(RUSTC) foo.rs -Zsave-analysis

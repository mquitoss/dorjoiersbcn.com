#JADE = $(shell find src/jade/*.jade)
#HTML = $(patsubst src/jade/%.jade, build/%.html, $(JADE))
#
#LESS = $(shell find src/less/*.less)
#CSS = $(patsubst src/less/%.less, build/css/%.css, $(LESS))

TARGET_DIR = build
CSS_DIR = $(TARGET_DIR)/css

HTML = build/index.html
CSS = build/css/style.css

all: $(HTML) $(CSS)

$(TARGET_DIR):
	mkdir $(TARGET_DIR)

$(CSS_DIR): $(TARGET_DIR)
	mkdir $(CSS_DIR)

build/%.html: src/jade/%.jade $(TARGET_DIR)
	jade < $< --out $< --path $< --pretty > $@

build/css/%.css: src/less/%.less $(CSS_DIR)
	lessc $< > $@

clean:
	rm -f $(HTML)
	rm -rf $(CSS_DIR)
	rm -rf $(TARGET_DIR)

.PHONY: clean


.PHONY: all
all:
	@echo "**********************************************************"
	@echo "**                    app build tool                    **"
	@echo "**********************************************************"


build:
	docker build -t app -f ./Dockerfile ../app


run:
	docker run -p 3000:3000 app

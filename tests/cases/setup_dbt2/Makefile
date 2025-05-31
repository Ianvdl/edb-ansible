include ../../Makefile.mk

build-rocky9:
	docker compose up primary1-rocky9 -d
	docker compose up dbt2_driver1-rocky9 -d
	docker compose up dbt2_client1-rocky9 -d

build-almalinux8:
	docker compose up primary1-almalinux8 -d
	docker compose up dbt2_driver1-almalinux8 -d
	docker compose up dbt2_client1-almalinux8 -d

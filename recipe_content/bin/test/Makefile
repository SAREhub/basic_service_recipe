LOCAL_REGISTRY_PORT = 5000
export IMAGE_NAMESPACE = localhost:$(LOCAL_REGISTRY_PORT)
export VERSION = test

## Runs docker local registry container for pushing test images
test_init_local_registry:
	docker run -d -p $(LOCAL_REGISTRY_PORT):5000 --restart=always --name registry registry:2

## Clean test env and inits all depending services like database
test_init: test_clean test_init_base

## Creates test secrets and network
test_init_base:
	bash ${BIN_SCRIPTS_PATH}/init.sh

## Clean test env
test_clean:
	bash ${BIN_SCRIPTS_PATH}/clean.sh

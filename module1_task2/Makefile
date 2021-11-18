build : ## Genera la pagina web con Hugo y la guarda en dist
	hugo -D > /dev/null 2>&1

.PHONY: clean
clean : ## Elimina el directorio dist
	rm -rf ./dist/ > /dev/null 2>&1

post : ## Crea un nuevo post, hace uso de las variables POST_NAME el cual tiene el nombre del archivo y POST_TITLE que le da el nombre al post
	hugo new posts/$(POST_NAME).md
	echo '---\ntitle: "$(POST_TITLE)"\ndate: 2010-03=26T08:47:11+01:00\ndraft: false\n---' > ./content/posts/$(POST_NAME).md
	
help : ## Ayuda y descripción de los comandos usados
	grep '##' ./Makefile | sed 's/ ##/ /' | head -n -1

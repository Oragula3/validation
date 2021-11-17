build :
	hugo -D > /dev/null 2>&1

.PHONY: clean
clean :
	rm -rf ./dist/ > /dev/null 2>&1

post :
	hugo new posts/$(POST_NAME).md
	echo '---\ntitle: "$(POST_TITLE)"\ndate: 2010-03=26T08:47:11+01:00\ndraft: false\n---' > ./content/posts/$(POST_NAME).md

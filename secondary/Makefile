
.PHONY: sync clean
sync: clean
	rsync -a example.jp.zone.origin example.jp.zone
	rsync -a example.jp.rev.origin example.jp.rev

clean:
	$(RM) db-* example.jp.zone example.jp.rev


MSGLANGS=$(notdir $(wildcard *.po))

MSGOBJS=$(addprefix locale/,$(MSGLANGS:.po=/LC_MESSAGES/pamac.mo))

gettext: ../data/polkit/org.manjaro.pamac.policy.in $(MSGOBJS)
	itstool -j ../data/polkit/org.manjaro.pamac.policy.in -o ../data/polkit/org.manjaro.pamac.policy $(MSGLANGS:.po=.mo)

clean:
	rm -rf locale
	rm -f *.mo
	rm -f ../data/polkit/org.manjaro.pamac.policy

locale/%/LC_MESSAGES/pamac.mo: %.po
	msgfmt -c -o $*.mo $*.po
	mkdir -p $(dir $@)
	cp $*.mo $(dir $@)pamac.mo

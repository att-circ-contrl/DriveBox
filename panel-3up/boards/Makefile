default: helpscreen

helpscreen:
	@echo ""
	@echo "Targets:  clean  pics  seeed"
	@echo ""

clean:
	rm -f plots/*
	rm -f packages/*

pics:
	cd gerber; pcb2png motor-panel-3up motor-panel.png; mv *png ../plots
	cd gerber; pcb2png motor-daughter-3up motor-daughter.png; mv *png ../plots

seeed:
	cd gerber; pcb2seeed motor-panel-3up motor-panel; mv *zip ../packages
	cd gerber; pcb2seeed motor-daughter-3up motor-daughter; mv *zip ../packages


#
# This is the end of the file.

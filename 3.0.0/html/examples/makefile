INPUTS:= $(wildcard *.jsonld)
OUTPUT-RDF=$(patsubst %.jsonld,%.nt,${INPUTS})
OUTPUT-TTL=$(patsubst %.jsonld,%.ttl,${INPUTS})

%.nt: %.jsonld
	rdf serialize --input-format jsonld --processingMode json-ld-1.1 $(CURDIR)/$< --output $(CURDIR)/$@

%.ttl: %.jsonld
	rdf serialize --output-format turtle --input-format jsonld --processingMode json-ld-1.1 \
		--prefixes "dcat:http://www.w3.org/ns/dcat#,dct:http://purl.org/dc/terms/,rdf:http://www.w3.org/1999/02/22-rdf-syntax-ns#,nal-frequency:http://publications.europa.eu/resource/authority/frequency/,example:https://data.gov.gr/,example-ds:https://data.gov.gr/id/dataset/,example-cat:https://data.gov.gr/id/catalog/,example-ser:https://data.gov.gr/id/datasetseries/,example-ag:https://agencies.gov.gr/id/ "\
		$(CURDIR)/$< --output $(CURDIR)/$@

all: ${OUTPUT-TTL}

clean:
	rm -rf ${OUTPUT-RDF} ${OUTPUT-TTL}



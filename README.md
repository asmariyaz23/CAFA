This is a tool for creating customized benchmarks for assessing protein function prediction methods. 

Usage:

python Benchmark --input1 <filename or time point> --input2 <filename or time point>

There are a bunch of optional parameters too. To view the entire list type the following:
python Benchmark --help

The output should contain 2 files. A tab delimited file containing the actual benchmark and a .png file showing the distribution of proteins in different ontologies. In the event if we get a benchmark file with no proteins in them, then there will be no output files.

Given a protein function prediction method, how do we assess the quality of the method in predicting a variety of target proteins?

It is a challenge to find proteins whose function has been experimentally determined and which can be used as a benchmark for assessment. This program helps users find that benchmark set based on their choice of organism, ontology etc. 

There can be 2 kinds of users for this program. One set of users are participants of the CAFA competition. They are given a target set of proteins to test their method on.At the point of giving the targets, all of them only have electronic annotations associated with them. Within acertain period of 'x' months, some of these targets will receive experimental annotations and can be used as benchmarks for assessing the user's predictions. So, these users can provide the initial target set as their input to the program along with the version of uniprot-goa thatthey would like to consider for creating the benchmarks. The idea is some proteins from the target set would have received experimental annotations within these 'x' months and only those will form the benchmark set. The version will be in the form of mm_yyyy. The idea is that the more recent the version is, the probability of having more benchmarks is higher.The output will be a file containing the list of benchmark proteins. Along with providing a specific version, users can also customize their benchmarks by providing organisms, ontologies and GO evidencethat they would like to consider. If users don't provide any values for these fields, default values would be used.

The other type of user who can use this program need not necessarily be a CAFA participant. He/she just has a prediction method that they would like assess through a benchmark. In such a case, the user might already have a target set or they would like to download one from uniprot-goa. If they don't have a target set of proteins, the input would be a version of uniprot that will be a target set. This version might contain both experimentally and electronically derived annotations. The other input would be a version (definitely later than the first one) that also contains proteins with both experimental and electronic annotations. The idea is that some proteins that were electronically annotated in the first set would have received exp validations in the second set. Those are the ones that can be used to create the benchmark set.As before, users can filter the final set based on their choice.


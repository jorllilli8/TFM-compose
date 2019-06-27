FROM jorllilli8/tfm-2019:hadoop
RUN /hadoop/bin/hadoop jar hadoop/share/hadoop/tools/lib/hadoop-streaming-2.9.2.jar -D stream.num.map.output.key.fields=10 -D mapred.text.key.partitioner.options=-k1,2,3,4 -mapper "python mapperOcu.py" -reducer "python reducerOcu.py" -input "datasetBicisProva.txt" -output outputBicis
RUN /hadoop/bin/hadoop jar /hadoop/share/hadoop/tools/lib/hadoop-streaming-2.9.2.jar -D stream.num.map.output.key.fields=10 -D mapred.text.key.partitioner.options=-k1,2,3,4 -mapper "python mapperSat.py" -reducer "python reducerSat.py" -input "datasetBicisProva.txt" -output outputBicisSat 
CMD python actualizeDB.py

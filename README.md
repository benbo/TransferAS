# MemexAS
Active Search (AS) wrapper to conduct AS on deduplicated texts and transfer labels unto a new corpus

##Dependencies##
- numpy
- scipy 
- cython
- scikit-learn

##Installation##

        wget https://github.com/benbo/MemexAS/archive/master.zip  
        unzip master.zip  
        mv MemexAS-master MemexAS  
        cd MemexAS  
        #build a fast ngram cython function  
        python setup.py build_ext --inplace  
        #Additionally, you need to download the following file into the same directory 
        wget https://raw.githubusercontent.com/AutonlabCMU/ActiveSearch/sibi/kernelAS/python/activeSearchInterface.py

##Example##
If you have followed those steps then you should be able to use the MemexAS class in MemexAS.py

        from os import listdir  
        from os.path import join  
        import MemexAS  
        myAS=MemexAS.MemexAS()  
        mypath="mytext.txt"#path to a textfile where each line represents a document/Ad  
        text=[{'ad_id':i,'text':line.rstrip()} for i,line in enumerate(open(join(mypath,f),'r'))]
        startp=text[0][0]
        myAS.newActiveSearch(text,starting_points=[startp])  



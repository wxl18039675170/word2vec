1. **install package**
    
        pip install -r requirements.txt

2. **process corpus, form xml to text**

        python process_wiki.py ./data/zhwiki-latest-pages-articles.xml.bz2 ./data/wiki.zh.text

3. **process corpus, form tranditional to simplified**

        opencc -i ./data/wiki.zh.text -o ./data/wiki.zh.jian.text -c t2s.json
        
4. **process corpus, sub En and segmentation zh.jian**

        python word_segmentation.py
        
5. **train**

        python train.py ./data/train.txt ./model/wiki_zh_word2vec.model ./model/wiki_zh_vectors.txt
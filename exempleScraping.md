# Exemple de l'analyse des sentiments a partir de facebook
## cas d'exemple  :
post de facebook sur coupe de monde 2030 : 
https://web.facebook.com/MustaphaSwinga/posts/pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l

# Installation et Requirements

## Anaconda Installation

Pour exécuter ce Jupyter Notebook, vous pouvez installer Anaconda, qui est une distribution Python puissante utilisée pour la science des données et l'apprentissage automatique. Vous pouvez télécharger Anaconda depuis [ce lien](https://www.anaconda.com/products/distribution) et suivre les instructions d'installation spécifiques à votre système d'exploitation.
## Installation des Packages
Installez les packages nécessaires en utilisant pip depuis le terminal Powershell promp dans anaconda .
- pip install facebook_scraper
- pip install nltk 


```python
# ça marche pas pour les pages jusqu'a maintenant
#from facebook_scraper import get_posts

#for post in get_posts('nintendo' ,pages=13):
#    print('test')
#    print(post['text'][:50])
```

    WARNING:facebook_scraper.page_iterators:No raw posts (<article> elements) were found in this page.
    


```python
"""
Download comments for a public Facebook post.
"""

import facebook_scraper as fs

# get POST_ID from the URL of the post which can have the following structure:
# https://www.facebook.com/USER/posts/POST_ID
# https://www.facebook.com/groups/GROUP_ID/posts/POST_ID
POST_ID = "pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l"

# number of comments to download -- set this to True to download all comments
MAX_COMMENTS = 500

# get the post (this gives a generator)
gen = fs.get_posts(
    post_urls=[POST_ID],
    options={"comments": MAX_COMMENTS, "progress": True}
)

# take 1st element of the generator which is the post we requested
post = next(gen)

# extract the comments part
comments = post['comments_full']

# process comments as you want...
for comment in comments:

    # e.g. ...print them
    print(comment['comment_text'])

    # e.g. ...get the replies for them
    for reply in comment['replies']:
        print(' ', reply['comment_text'])
```

    WARNING:facebook_scraper.extractors:[pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l] Exception while running extract_user_id: KeyError('content_owner_id_new')
    WARNING:facebook_scraper.extractors:[pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l] Extract method extract_video didn't return anything
    WARNING:facebook_scraper.extractors:[pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l] Extract method extract_video_thumbnail didn't return anything
    WARNING:facebook_scraper.extractors:[pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l] Extract method extract_video_id didn't return anything
    WARNING:facebook_scraper.extractors:[pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l] Extract method extract_video_meta didn't return anything
    WARNING:facebook_scraper.extractors:[pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l] Extract method extract_factcheck didn't return anything
    WARNING:facebook_scraper.extractors:[pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l] Extract method extract_share_information didn't return anything
    WARNING:facebook_scraper.extractors:[pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l] Extract method extract_listing didn't return anything
    WARNING:facebook_scraper.extractors:[pfbid02bhaHCNCutE3S2p8S9Dsw7AeRTpDKEBE8qPENnZZChYSz14EBTi9kYgbArNuiwjn8l] Extract method extract_with didn't return anything
    


      0%|          | 0/500 [00:00<?, ?it/s]


    البنية التحتية فقط هي التي يمكن أن يستفاد منها ، الباقي ستكون إستفادة لحظية فقط . خير مثال جائحة كورونا و لم يستفد منها ...!!!!
      Abdelhamid Hajrifi كاتسنا تربح من جائحة ؟؟؟؟
      Abdelmonaime Chourafi دول كثيرة إستفادت من الجائحة في الوقت الذي لم نستفد منها شيئا ، أتحدث عن المنظومة الصحية المتهالكة ، البيروقراطية ، الخدمات الرقمية و غيرها ... إذا كنت تعتبر الربح شيئا آخر الله أعلم
      Abdelhamid Hajrifi
    هههه راك مافاهم والو أخويا
    غاحال فمك .. واش تتعرف شحال ديال العملة الصعبة غادي دخلها ليك كاس العالم بسباب شهرة ديال دولة ديالك فالعالم ؟ العالم كامل غادي يتعرف على المغرب و ملايين غادي يرجعو ليه بعد انتهاء كأس العالم فالسنوات الي تلي المونديال
    واش تيصحابلك الدول مكلخة باش تخسر ملايير الدولارات في تنظيم هذه التظاهرة هاكا غير صدقة ههههههه
      Khalid El Haddalahi تبارك عليك اخاي و الله ما كنت عارف ما سحابليش انت عارف هادشي كامل و الله العظيم عندك الصح ... فيق اخاي الله يهديك ...راه عاد كان عندنا الزلزال ، الهيليكوبتير ملقاتش منين دوز ...
      Khalid El Haddalahi
    العملة الصعبة مغتاخدهاش نتا ومغادي تستافد منها والو. نتا غادي تاخد غير الزيادة فل الأسعار براكة عليك.
      Abdelhamid Hajrifi
    ما علاقة فساد الدولة
    بالإستفادة من تظاهرة ؟
    حنا كنهضرو على واش هاد التظاهرة مفيدة للمغرب وانت تتجاوب بان المغرب فيه الفساد و الفقر الخ
    شحال الIQ ديالك اخويا هههههه
      البطاطس ب 50 درهم
      Soufiane Moutanabih
    هههههه هاد الفيسبوك فيه غالبسطاء
    سير أخويا تشري الحرشة و كاس ديالك القهوة وتفرج فالتشامبيونس هادشي بعيد عليك
    واش تتسنا يدقو عليك فالدار و يعطوك جوا فيه الفلوس ههههههه
    دير شي بحث فجوجل ووعرف كفاش للسياحة أنها تروج ليك الدولة .. على الاقل تفهم شنو طاري
      Khalid El Haddalahi ههههههههههههههه
    ههههههههههههههه
    ههههههههههههههه
    ههه
      Khalid El Haddalahi بصحتك العملة الصعبة والملايير ديال الدولار.
    أجي عندك بعدا فين تخبي العملة الصعبة أولا لا؟
      Abdelhamid Hajrifi يعني في نظرك كورونا كانت خاصها تجعلنا نتطورو ههههههههههههههه
    هههههههههههه
      Khalid El Haddalahi
    هذا غير تفكير العبي.د والمذلولين بحالك لاحاسين العرش وصحاب الزليج ديالنا والقطفان ديالنا ويااااااا ربحنا. تا واحد مكيتسنى الدولة تعطيه الفلوس فدار. ولكن حنا بغينا عير تعليم مزيان وصحة مزيانة وبنية تحتية مزيانة. هادي أمور بسيطة بغيناه ا وساهل جداً باش نحققوها ولكن لي مسؤولين على هاد البلاد كيضريو كلشي لجيبهم وشكون تيخلص؟ تيخلص المواطن الضعيف المقهور، عرفتي علاش؟ حيت كاينين العبي.د بحالك لي كيطبلو للتخربيق وكيقولوش الحق. گطع الله يدير خير وخا ما بان ليا خير مع المذلولين لي همهم غير الكرة والعهر.
   .................
    

## passage vers pandas (bibliotheque pour manipulation des dataframes )


```python
#importation de package pandas as pd
import pandas as pd
df = pd.json_normalize(comments, sep='_')
df.shape

```




    (510, 13)




```python
#extrait de donnes
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>comment_id</th>
      <th>comment_url</th>
      <th>commenter_id</th>
      <th>commenter_url</th>
      <th>commenter_name</th>
      <th>commenter_meta</th>
      <th>comment_text</th>
      <th>comment_time</th>
      <th>comment_image</th>
      <th>comment_reactors</th>
      <th>comment_reactions</th>
      <th>comment_reaction_count</th>
      <th>replies</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>163616990078043</td>
      <td>https://facebook.com/163616990078043</td>
      <td>100000434229818</td>
      <td>None</td>
      <td>Abdelhamid Hajrifi</td>
      <td>None</td>
      <td>البنية التحتية فقط هي التي يمكن أن يستفاد منها...</td>
      <td>2023-10-12</td>
      <td>None</td>
      <td>[]</td>
      <td>None</td>
      <td>None</td>
      <td>[{'comment_id': '245859991376592', 'comment_ur...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>336649735558185</td>
      <td>https://facebook.com/336649735558185</td>
      <td>100004767259454</td>
      <td>None</td>
      <td>Abderrahim Baalla</td>
      <td>None</td>
      <td>فرصة اقتصادية مزيانة باش تجذب الاستثمارات ، و ...</td>
      <td>2023-10-12</td>
      <td>None</td>
      <td>[]</td>
      <td>None</td>
      <td>None</td>
      <td>[{'comment_id': '774438894484417', 'comment_ur...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>333864169044501</td>
      <td>https://facebook.com/333864169044501</td>
      <td>100001654654191</td>
      <td>None</td>
      <td>Hanane Salma</td>
      <td>None</td>
      <td>تحية للأساتذة ✌🏻\n#معا_لرد_الاعتبا\nر_للأستاذ_...</td>
      <td>2023-10-12</td>
      <td>None</td>
      <td>[]</td>
      <td>None</td>
      <td>None</td>
      <td>[{'comment_id': '344416661489702', 'comment_ur...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1479996756173048</td>
      <td>https://facebook.com/1479996756173048</td>
      <td>100001866400174</td>
      <td>None</td>
      <td>Alae El Alami</td>
      <td>None</td>
      <td>أحسن حاجة هي يخدمو البنية التحتية ديال البلاد</td>
      <td>2023-10-12</td>
      <td>None</td>
      <td>[]</td>
      <td>None</td>
      <td>None</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>4</th>
      <td>276852758637432</td>
      <td>https://facebook.com/276852758637432</td>
      <td>100000857307632</td>
      <td>None</td>
      <td>رشيد المنصوري</td>
      <td>None</td>
      <td>لا شيء لم يعد المونديال التاثير الكبير على الا...</td>
      <td>2023-10-12</td>
      <td>None</td>
      <td>[]</td>
      <td>None</td>
      <td>None</td>
      <td>[]</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Sauvegarder le DataFrame dans un fichier CSV
df.to_csv('commentaires.csv', index=False)

```

# petite exemple d'analyse de text avec nltk (analyse basic)
NLTK (Natural Language Toolkit) est une bibliothèque Python puissante pour le traitement du langage naturel. Elle offre de nombreux outils et ressources pour analyser et traiter le texte.




```python
import nltk
nltk.download('punkt')
```

    [nltk_data] Downloading package punkt to
    [nltk_data]     C:\Users\sejja\AppData\Roaming\nltk_data...
    [nltk_data]   Unzipping tokenizers\punkt.zip.
    




    True




```python
nltk.download('stopwords')
```

    [nltk_data] Downloading package stopwords to
    [nltk_data]     C:\Users\sejja\AppData\Roaming\nltk_data...
    [nltk_data]   Unzipping corpora\stopwords.zip.
    




    True




```python
import pandas as pd
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords
from collections import Counter
import matplotlib.pyplot as plt

# Assurez-vous d'avoir nltk téléchargé
# nltk.download('punkt')
# nltk.download('stopwords')

# Supprimez les commentaires nuls ou vides
df = df.dropna(subset=['comment_text'])
df = df[df['comment_text'] != '']

# Concaténez tous les commentaires en une seule chaîne
all_comments = ' '.join(df['comment_text'])

# Tokenization
tokens = word_tokenize(all_comments)

# Supprimez la ponctuation et convertissez en minuscules
tokens = [word.lower() for word in tokens if word.isalpha()]

# Supprimez les stopwords
stop_words = set(stopwords.words('arabic'))  # Adapté pour l'arabe
tokens = [word for word in tokens if word not in stop_words]

# Comptez les occurrences de chaque mot
word_counts = Counter(tokens)

# Affichez les 10 mots les plus fréquents
most_common_words = word_counts.most_common(10)
print("Les 10 mots les plus fréquents :")
for word, count in most_common_words:
    print(f"{word}: {count}")

# Créez un graphique des mots les plus fréquents
plt.bar(*zip(*most_common_words))
plt.xlabel('Mots')
plt.ylabel('Fréquence')
plt.title('Top 10 des mots les plus fréquents')
plt.show()

```

    Les 10 mots les plus fréquents :
    غادي: 77
    التحتية: 59
    المغرب: 59
    البنية: 51
    الله: 48
    العالم: 47
    شي: 35
    باش: 33
    الشعب: 32
    تنظيم: 32
    


    
![png](output_11_1.png)
    


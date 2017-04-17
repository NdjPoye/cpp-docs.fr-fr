---
title: '&lt;fstream&gt;, typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4978b0b9f49fd0b0f4125c3dd2f17d07446bc6ac
ms.lasthandoff: 02/24/2017

---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt;, typedefs
||||  
|-|-|-|  
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|  
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|  
|[wifstream](#wifstream)|[wofstream](#wofstream)|  
  
##  <a name="a-namefilebufa--filebuf"></a><a name="filebuf"></a>  filebuf  
 Type `basic_filebuf` spécialisé sur des paramètres de modèle `char`.  
  
```
typedef basic_filebuf<char, char_traits<char>> filebuf;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_filebuf](../standard-library/basic-filebuf-class.md) spécialisée pour les éléments de type `char` ayant les caractéristiques par défaut.  
  
##  <a name="a-namefstreama--fstream"></a><a name="fstream"></a>  fstream  
 Type `basic_fstream` spécialisé sur des paramètres de modèle `char`.  
  
```
typedef basic_fstream<char, char_traits<char>> fstream;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_fstream](../standard-library/basic-fstream-class.md) spécialisée pour les éléments de type `char` ayant les caractéristiques par défaut.  
  
##  <a name="a-nameifstreama--ifstream"></a><a name="ifstream"></a>  ifstream  
 Définit un flux à utiliser pour lire les données codées sur un octet de façon séquentielle dans un fichier. `ifstream` est un typedef qui spécialise la classe de modèles `basic_ifstream` pour `char`.  
  
 `wifstream` est un typedef qui spécialise `basic_ifstream` pour la lecture des caractères double largeur `wchar_t`. Pour plus d’informations, consultez [wifstream](../standard-library/fstream-typedefs.md#wifstream).  
  
```
typedef basic_ifstream<char, char_traits<char>> ifstream;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèles `basic_ifstream`, spécialisée pour les éléments de type char ayant les traits de caractère par défaut. Voici un exemple :  
  
 `using namespace std;`  
  
 `ifstream infile("existingtextfile.txt");`  
  
 `if (!infile.bad())`  
  
 `{`  
  
 `// Dump the contents of the file to cout.`  
  
 `cout << infile.rdbuf();`  
  
 `infile.close();`  
  
 `}`  
  
##  <a name="a-nameofstreama--ofstream"></a><a name="ofstream"></a>  ofstream  
 Type `basic_ofstream` spécialisé sur des paramètres de modèle `char`.  
  
```
typedef basic_ofstream<char, char_traits<char>> ofstream;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_ofstream](../standard-library/basic-ofstream-class.md) spécialisée pour les éléments de type `char` ayant les caractéristiques par défaut.  
  
##  <a name="a-namewfstreama--wfstream"></a><a name="wfstream"></a>  wfstream  
 Type `basic_fstream` spécialisé sur des paramètres de modèle `wchar_t`.  
  
```
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_fstream](../standard-library/basic-fstream-class.md) spécialisée pour les éléments de type `wchar_t` ayant les caractéristiques par défaut.  
  
##  <a name="a-namewifstreama--wifstream"></a><a name="wifstream"></a>  wifstream  
 Type `basic_ifstream` spécialisé sur des paramètres de modèle `wchar_t`.  
  
```
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_ifstream](../standard-library/basic-ifstream-class.md) spécialisée pour les éléments de type `wchar_t` ayant les caractéristiques par défaut.  
  
##  <a name="a-namewofstreama--wofstream"></a><a name="wofstream"></a>  wofstream  
 Type `basic_ofstream` spécialisé sur des paramètres de modèle `wchar_t`.  
  
```
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_ofstream](../standard-library/basic-ofstream-class.md) spécialisée pour les éléments de type `wchar_t` ayant les caractéristiques par défaut.  
  
##  <a name="a-namewfilebufa--wfilebuf"></a><a name="wfilebuf"></a>  wfilebuf  
 Type `basic_filebuf` spécialisé sur des paramètres de modèle `wchar_t`.  
  
```
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_filebuf](../standard-library/basic-filebuf-class.md) spécialisée pour les éléments de type `wchar_t` ayant les caractéristiques par défaut.  
  
## <a name="see-also"></a>Voir aussi  
 [\<fstream>](../standard-library/fstream.md)




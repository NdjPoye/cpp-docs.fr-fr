---
title: "Erreur des outils &#201;diteur de liens LNK2005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2005"
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Erreur des outils &#201;diteur de liens LNK2005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbole déjà défini dans l'objet  
  
 Le `symbol` donné, affiché dans sa forme décorée, a été défini plusieurs fois.  
  
 Pour plus d'informations, voir les articles suivants de la Base de connaissances :  
  
-   « Des erreurs LNK2005 se produisent lorsque des bibliothèques CRT de liens sont liées avant des bibliothèques MFC » \(Q148652\)  
  
-   « Un opérateur delete surchargé global entraîne une erreur LNK2005 » \(Q140440\)  
  
-   « Des erreurs LNK2005 se produisent pour les opérateurs New et Delete lors de la définition de \_ATL\_MIN\_CRT » \(Q184235\).  
  
 Vous trouverez les articles de la Base de connaissances sur le CD\-ROM MSDN Library ou à l'adresse [http:\/\/support.microsoft.com\/search](http://support.microsoft.com/search).  
  
 Cette erreur est suivie de l'erreur irrécupérable [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).  
  
### Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Combinaison de bibliothèques statiques et dynamiques tout en utilisant [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
2.  Le symbole est une fonction packagée \(créée par la compilation avec [\/Gy](../../build/reference/gy-enable-function-level-linking.md)\) et était inclus dans plusieurs fichiers, mais a été modifié entre les compilations.  Recompilez tous les fichiers qui incluent `symbol`.  
  
3.  Le symbole est défini différemment dans deux objets membres dans des bibliothèques différentes, et les deux objets membres ont été utilisés.  
  
4.  Un élément absolu est défini deux fois, avec une valeur différente dans chaque définition.  
  
5.  Un fichier d'en\-tête a déclaré et défini une variable.  Plusieurs solutions sont possibles :  
  
    -   Déclarez la variable dans .h : `extern BOOL MyBool;` puis affectez\-lui une valeur dans un fichier .c ou .cpp : `BOOL MyBool = FALSE;`.  
  
    -   Déclarez la variable [static](../../misc/static-cpp.md).  
  
    -   Déclarez la variable [selectany](../../cpp/selectany.md).  
  
6.  Vous utilisez uuid.lib en association avec d'autres fichiers .lib qui définissent des identificateurs GUID \(par exemple, oledb.lib et adsiid.lib\).  Par exemple :  
  
    ```  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     Pour corriger le problème, ajoutez [\/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md) dans les options de ligne de commande de l'éditeur de liens, et assurez\-vous que uuid.lib est la première bibliothèque référencée.
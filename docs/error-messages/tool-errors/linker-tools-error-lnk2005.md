---
title: "Erreur LNK2005 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2005
dev_langs:
- C++
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: bf93f364b3dc7156a62eb1c474177eb7b85c7827
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2005"></a>Erreur des outils Éditeur de liens LNK2005
symbole déjà défini dans l'objet  
  
Le `symbol` donné, affiché dans sa forme décorée, a été défini plusieurs fois.  
  
Pour plus d'informations, voir les articles suivants de la Base de connaissances :  
  
-   [Une erreur LNK2005 se produit lorsque la bibliothèque CRT et les bibliothèques MFC sont liées dans un ordre incorrect dans Visual C++](https://support.microsoft.com/kb/148652)  
  
-   [CORRECTIF : Delete surchargé Global opérateur Causes LNK2005](https://support.microsoft.com/kb/140440)  
  
-   [Vous recevez des erreurs LNK2005 se produisent lorsque vous compilez un projet exécutable (.exe) de ATL dans Visual C++](https://support.microsoft.com/kb/184235).  
  
Cette erreur est suivie d’une erreur irrécupérable [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md).  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Mélange de bibliothèques statiques et dynamiques en utilisant [/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
2.  Le symbole est une fonction packagée (créée par compilation avec [/Gy](../../build/reference/gy-enable-function-level-linking.md)) et a été inclus dans plus d’un fichier mais a été modifié entre les compilations. Recompilez tous les fichiers qui incluent `symbol`.  
  
3.  Le symbole est défini différemment dans deux objets membres dans des bibliothèques différentes, et les deux objets membres ont été utilisés.  
  
4.  Un élément absolu est défini deux fois, avec une valeur différente dans chaque définition.  
  
5.  Un fichier d'en-tête a déclaré et défini une variable. Plusieurs solutions sont possibles :  
  
    -   Déclarez la variable dans .h : `extern BOOL MyBool;` puis affectez-lui une valeur dans un fichier .c ou .cpp : `BOOL MyBool = FALSE;`.  
  
    -   Déclarez la variable [statique](../../cpp/storage-classes-cpp.md#static).  
  
    -   Déclarez la variable [selectany](../../cpp/selectany.md).  
  
6.  Vous utilisez uuid.lib en association avec d'autres fichiers .lib qui définissent des identificateurs GUID (par exemple, oledb.lib et adsiid.lib). Exemple :  
  
    ```  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     Pour corriger, ajoutez [/force : multiple](../../build/reference/force-force-file-output.md) dans les options de ligne de commande de l’éditeur de liens et assurez-vous que uuid.lib est la première bibliothèque référencée.

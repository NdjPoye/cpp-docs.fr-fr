---
title: "Construction d’objets de flux d’entrée │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7e8c664bd6632f480ba53b9dedea914bbc8e4dd7
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="constructing-input-stream-objects"></a>Construction d'objets de flux d'entrée
Si vous utilisez uniquement l’objet `cin`, vous n’avez pas besoin de construire un flux d’entrée. Vous devez construire un flux d’entrée si vous utilisez les éléments suivants :  
  
- [Constructeurs de flux de fichier d’entrée](#vclrfinputfilestreamconstructorsanchor8)  
  
- [Constructeurs de flux de chaîne d’entrée](#vclrfinputstringstreamconstructorsanchor9)  
  
##  <a name="vclrfinputfilestreamconstructorsanchor8"></a> Constructeurs de flux de fichier d’entrée  
 Il existe deux façons de créer un flux de fichier d’entrée :  
  
-   Utilisez le constructeur de l’argument `void`, puis appelez la fonction membre `open` :  
  
 ```  
    ifstream myFile; // On the stack  
    myFile.open("filename");

 
    ifstream* pmyFile = new ifstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   Spécifiez un nom de fichier et des indicateurs de mode dans l’appel du constructeur, pour l’ouverture du fichier pendant le processus de construction :  
  
 ```  
    ifstream myFile("filename");
```  
  
##  <a name="vclrfinputstringstreamconstructorsanchor9"></a> Constructeurs de flux de chaîne d’entrée  
 Les constructeurs de flux de chaîne d’entrée nécessitent l’adresse du stockage préalloué et préinitialisé :  
  
```  
string s("123.45");

double amt;  
istringstream myString(s);

//istringstream myString("123.45") also works  
myString>> amt; // amt contains 123.45  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Flux d’entrée](../standard-library/input-streams.md)



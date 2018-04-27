---
title: Construction d’objets de flux d’entrée │ Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a63ba3d8e54e416313ec24d7455ca4cf70979b9f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="constructing-input-stream-objects"></a>Construction d'objets de flux d'entrée

Si vous utilisez uniquement l’objet `cin`, vous n’avez pas besoin de construire un flux d’entrée. Vous devez construire un flux d’entrée si vous utilisez les éléments suivants :

- [Constructeurs de flux de fichier d’entrée](#vclrfinputfilestreamconstructorsanchor8)

- [Constructeurs de flux de chaîne d’entrée](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a> Constructeurs de flux de fichier d’entrée

Il existe deux façons de créer un flux de fichier d’entrée :

- Utilisez le constructeur de l’argument `void`, puis appelez la fonction membre `open` :

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- Spécifiez un nom de fichier et des indicateurs de mode dans l’appel du constructeur, pour l’ouverture du fichier pendant le processus de construction :

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="vclrfinputstringstreamconstructorsanchor9"></a> Constructeurs de flux de chaîne d’entrée

Les constructeurs de flux de chaîne d’entrée nécessitent l’adresse du stockage préalloué et préinitialisé :

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>Voir aussi

[Flux d’entrée](../standard-library/input-streams.md)<br/>

---
title: "Erreur LNK1312 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1312
dev_langs: C++
helpviewer_keywords: LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0fc7bf47ff05f817b36ff9ff641fe7823aa38d9a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1312"></a>Erreur des outils Éditeur de liens LNK1312
fichier non valide ou endommagé : Impossible d’importer l’assembly  
  
 Lors de la création d’un assembly, un fichier autre qu’un module ou un assembly compilé avec **/CLR** a été passé à la **/ASSEMBLYMODULE** option de l’éditeur de liens.  Si vous avez passé un fichier objet à **/ASSEMBLYMODULE**, simplement passer l’objet directement à l’éditeur de liens, plutôt qu’à **/ASSEMBLYMODULE**.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant créé le fichier .obj.  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur LNK1312.  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```
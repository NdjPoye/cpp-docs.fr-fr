---
title: "&lt;fstream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<fstream>"
  - "<fstream>"
  - "std.<fstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fstream (en-tête)"
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;fstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit plusieurs classes qui prennent en charge les opérations iostreams sur des séquences stockées dans des fichiers externes.  
  
## Syntaxe  
  
```  
  
#include <fstream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[filebuf](../Topic/filebuf.md)|Type `basic_filebuf` spécialisé sur des paramètres de modèle `char`.|  
|[fstream](../Topic/fstream.md)|Type `basic_fstream` spécialisé sur des paramètres de modèle `char`.|  
|[ifstream](../Topic/ifstream.md)|Type `basic_ifstream` spécialisé sur des paramètres de modèle `char`.|  
|[ofstream](../Topic/ofstream.md)|Type `basic_ofstream` spécialisé sur des paramètres de modèle `char`.|  
|[wfstream](../Topic/wfstream.md)|Type `basic_fstream` spécialisé sur des paramètres de modèle `wchar_t`.|  
|[wifstream](../Topic/wifstream.md)|Type `basic_ifstream` spécialisé sur des paramètres de modèle `wchar_t`.|  
|[wofstream](../Topic/wofstream.md)|Type `basic_ofstream` spécialisé sur des paramètres de modèle `wchar_t`.|  
|[wfilebuf](../Topic/wfilebuf.md)|Type `basic_filebuf` spécialisé sur des paramètres de modèle `wchar_t`.|  
  
### Classes  
  
|||  
|-|-|  
|[basic\_filebuf](../standard-library/basic-filebuf-class.md)|La classe de modèle décrit une mémoire tampon de flux qui contrôle la transmission d'éléments de type **Elem**, dont les caractéristiques sont déterminées par la classe **Tr**, vers et à partir d'une séquence d'éléments stockée dans un fichier externe.|  
|[basic\_fstream](../standard-library/basic-fstream-class.md)|La classe de modèle décrit un objet qui contrôle l'insertion et l'extraction d'éléments et d'objets encodés à l'aide d'une mémoire tampon de flux de classe [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\>, avec des éléments de type **Elem**, dont les caractéristiques sont déterminées par la classe **Tr**.|  
|[basic\_ifstream](../standard-library/basic-ifstream-class.md)|La classe de modèle décrit un objet qui contrôle l'extraction d'éléments et d'objets encodés à partir d'une mémoire tampon de flux de classe [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\>, avec des éléments de type **Elem**, dont les caractéristiques sont déterminées par la classe **Tr**.|  
|[basic\_ofstream](../standard-library/basic-ofstream-class.md)|La classe de modèle décrit un objet qui contrôle l'insertion d'éléments et d'objets encodés dans une mémoire tampon de flux de classe [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\>, avec des éléments de type **Elem**, dont les caractéristiques sont déterminées par la classe **Tr**.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)
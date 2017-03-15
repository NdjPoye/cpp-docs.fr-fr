---
title: "Stand-Alone Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "standalone attributes"
  - "attributes [C++], standalone"
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Stand-Alone Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un attribut autonome ne traite le mot clé C\+\+ mais est plus proche d'une ligne de code.  Les instructions autonomes d'attribut requièrent un point\-virgule à la fin de la ligne.  
  
|Attribut|Description|  
|--------------|-----------------|  
|[cpp\_quote](../windows/cpp-quote.md)|Effectue la chaîne spécifiée, sans guillemets, dans le fichier d'en\-tête généré.|  
|[custom](../windows/custom-cpp.md)|Vous permet de définir votre propre attribut.|  
|[db\_command](../windows/db-command.md)|Crée une commande OLE DB.|  
|[emitidl](../windows/emitidl.md)|Détermine si tous les attributs suivants IDL seront traités et placés dans le fichier généré .idl.|  
|[idl\_module](../windows/idl-module.md)|Spécifie un point d'entrée dans une DLL.|  
|[idl\_quote](../windows/idl-quote.md)|Vous permet d'utiliser les éléments IDL qui ne sont pas pris en charge dans la version actuelle de Visual C\+\+ et pour les faire passer le fichier généré .idl.|  
|[import](../windows/import.md)|Spécifie un autre fichier .idl, .odl, ou .h contenant des définitions que vous souhaitez référencer à partir de votre fichier principal .idl.|  
|[importidl](../windows/importidl.md)|Insère le fichier spécifié .idl dans le fichier généré .idl|  
|[importlib](../windows/importlib.md)|Rend les types qui ont déjà été compilés dans une autre bibliothèque de types disponible dans la bibliothèque de types est créée.|  
|[incluez](../windows/include-cpp.md)|Spécifie un ou plusieurs fichiers d'en\-tête à inclure dans le fichier généré .idl.|  
|[includelib](../windows/includelib-cpp.md)|Génère un fichier .idl ou .h à inclure dans le fichier généré .idl.|  
|[library\_block](../windows/library-block.md)|Place un élément à l'intérieur de le bloc bibliothèque du fichier .idl.|  
|[module](../windows/module-cpp.md)|Définit le bloc bibliothèque dans le fichier .idl.|  
|[no\_injected\_text](../windows/no-injected-text.md)|Le compilateur ne pourra pas d'injecter du code résultant de l'utilisation d'attributs.|  
|[pragma](../windows/pragma.md)|Effectue la chaîne spécifiée, sans guillemets, dans le fichier généré .idl.|  
  
## Voir aussi  
 [Attributes by Usage](../windows/attributes-by-usage.md)
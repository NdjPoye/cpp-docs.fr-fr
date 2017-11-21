---
title: Attributs autonomes | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- standalone attributes
- attributes [C++], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 17009c1e9c1f7a771b717a96d1aadc4a680fe78f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="stand-alone-attributes"></a>Attributs autonomes
Un attribut autonome ne fonctionne pas sur un mot clé C++ mais est similaire à une ligne de code. Les instructions d’attribut autonome nécessitent un point-virgule à la fin de la ligne.  
  
|Attribut|Description|  
|---------------|-----------------|  
|[cpp_quote](../windows/cpp-quote.md)|Émet la chaîne spécifiée, sans guillemets, dans le fichier d’en-tête généré.|  
|[personnalisé](../windows/custom-cpp.md)|Permet de définir votre propre attribut.|  
|[db_command](../windows/db-command.md)|Crée une commande OLE DB.|  
|[emitidl](../windows/emitidl.md)|Détermine si tous les attributs IDL suivantes seront traités et placés dans le fichier .idl généré.|  
|[idl_module](../windows/idl-module.md)|Spécifie un point d’entrée dans une DLL.|  
|[idl_quote](../windows/idl-quote.md)|Vous pouvez utiliser des constructions IDL qui ne sont pas pris en charge dans la version actuelle de Visual C++ et les transmettre au fichier .idl généré.|  
|[import](../windows/import.md)|Spécifie un autre fichier .idl et .h .odl contenant les définitions à référencer à partir de votre fichier .idl principal.|  
|[importidl](../windows/importidl.md)|Insère un fichier .idl spécifié dans le fichier .idl généré|  
|[importlib](../windows/importlib.md)|Rend disponibles les types qui ont déjà été compilés dans une autre bibliothèque de types pour la bibliothèque de types en cours de création.|  
|[include](../windows/include-cpp.md)|Spécifie un ou plusieurs fichiers d’en-tête à inclure dans le fichier .idl généré.|  
|[includelib](../windows/includelib-cpp.md)|Génère un fichier .idl ou .h à inclure dans le fichier .idl généré.|  
|[library_block](../windows/library-block.md)|Place une construction à l’intérieur du bloc de bibliothèque du fichier .idl.|  
|[module](../windows/module-cpp.md)|Définit le bloc de bibliothèque dans le fichier .idl.|  
|[no_injected_text](../windows/no-injected-text.md)|Empêche le compilateur d’injecter du code à la suite d’utilisation de l’attribut.|  
|[pragma](../windows/pragma.md)|Émet la chaîne spécifiée, sans guillemets, dans le fichier .idl généré.|  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs par utilisation](../windows/attributes-by-usage.md)
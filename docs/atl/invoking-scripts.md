---
title: "Invoking Scripts | Microsoft Docs"
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
  - "StringRegister"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scripts, invoking registry in ATL"
  - "StringRegister method"
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Invoking Scripts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Utilisation de paramètres remplaçables \(le préprocesseur du registre\)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) traite des tables de remplacement et mentionne la méthode **AddReplacement**d'inscription.  Le registre contient huit autres méthodes spécifiques au script, et sont tous décrits dans le tableau suivant.  
  
|Méthode|Description et syntaxe|  
|-------------|----------------------------|  
|**ResourceRegister**|*resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType`\);de**HRESULT ResourceRegister\( LPCOLESTR**<br /><br /> Enregistre le script contenu dans la ressource d'un module.  *le resFileName* indique le chemin d'accès UNC au module lui\-même.  `nID` et `szType` contiennent l'ID de la ressource et tapez, respectivement.|  
|**ResourceUnregister**|*resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType`\);de**HRESULT ResourceUnregister\( LPCOLESTR**<br /><br /> Annule l'inscription le script contenu dans la ressource d'un module.  *le resFileName* indique le chemin d'accès UNC au module lui\-même.  `nID` et `szType` contiennent l'ID de la ressource et tapez, respectivement.|  
|**ResourceRegisterSz**|*szID* **, LPCOLESTR**  `szType`\);de**, LPCOLESTR** de*resFileName de***HRESULT ResourceRegisterSz\( LPCOLESTR**<br /><br /> Enregistre le script contenu dans la ressource d'un module.  *le resFileName* indique le chemin d'accès UNC au module lui\-même.  *le szID* et l' `szType` contiennent l'identificateur de chaîne de la ressource et tapez, respectivement.|  
|**ResourceUnregisterSz**|*szID* **, LPCOLESTR**  `szType`\);de**, LPCOLESTR** de*resFileName de***HRESULT ResourceUnregisterSz\( LPCOLESTR**<br /><br /> Annule l'inscription le script contenu dans la ressource d'un module.  *le resFileName* indique le chemin d'accès UNC au module lui\-même.  *le szID* et l' `szType` contiennent l'identificateur de chaîne de la ressource et tapez, respectivement.|  
|**FileRegister**|*nom du fichier* \);de**HRESULT FileRegister\( LPCOLESTR**<br /><br /> Enregistre le script dans un fichier.  *le nom de fichier* est un chemin UNC vers un fichier qui contient \(ou\) est un script de ressources.|  
|**FileUnregister**|*nom du fichier* \);de**HRESULT FileUnregister\( LPCOLESTR**<br /><br /> Annule l'inscription du script dans un fichier.  *le nom de fichier* est un chemin UNC vers un fichier qui contient \(ou\) est un script de ressources.|  
|**StringRegister**|*données* \);de**HRESULT StringRegister\( LPCOLESTR**<br /><br /> Enregistre le script dans une chaîne.  *les données* contiennent le script lui\-même.|  
|**StringUnregister**|*données* \);de**HRESULT StringUnregister\( LPCOLESTR**<br /><br /> Annule l'inscription du script dans une chaîne.  *les données* contiennent le script lui\-même.|  
  
 **ResourceRegisterSz** et **ResourceUnregisterSz**, sont semblables à **ResourceRegister** et à **ResourceUnregister**, mais vous permettent de spécifier un identificateur de chaîne.  
  
 Les méthodes **FileRegister** et **FileUnregister** sont utiles si vous ne souhaitez pas de script dans une ressource ou si vous souhaitez que le script dans son propre fichier.  Les méthodes **StringRegister** et **StringUnregister** permettent le fichier .rgs à stocker dans une chaîne allouée dynamiquement.  
  
## Voir aussi  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
---
title: "FtmBase, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FtmBase (classe)"
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un objet de marshaler libre de threads.  
  
## Syntaxe  
  
```  
  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags< WinRtClassicComMix >,   
   Microsoft::WRL::CloakedIid< IMarshal > >;  
```  
  
## Remarques  
 Pour plus d'informations, consultez la rubrique « IMarshal » dans la sous\-rubrique « Interfaces COM » de la rubrique « Référence COM » dans la bibliothèque MSDN.  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[FtmBase::FtmBase, constructeur](../windows/ftmbase-ftmbase-constructor.md)|Initialise une nouvelle instance de la classe FtmBase.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[FtmBase::CreateGlobalInterfaceTable, méthode](../windows/ftmbase-createglobalinterfacetable-method.md)|Crée un tableau global d'interface \(GIT\).|  
|[FtmBase::DisconnectObject, méthode](../windows/ftmbase-disconnectobject-method.md)|Libère de force toutes les connexions externes à un objet.  Le serveur de l'objet appelle l'implémentation de l'objet de cette méthode avant de s'arrêter.|  
|[FtmBase::GetMarshalSizeMax, méthode](../windows/ftmbase-getmarshalsizemax-method.md)|Obtient la limite supérieure du nombre d'octets nécéssaires pour marshaler le pointeur d'interface spécifié sur l'objet spécifié.|  
|[FtmBase::GetUnmarshalClass, méthode](../windows/ftmbase-getunmarshalclass-method.md)|Obtient le CLSID que COM utilise pour localiser la DLL contenant le code du proxy correspondant.  COM charge cette DLL pour créer une instance non initialisée du proxy.|  
|[FtmBase::MarshalInterface, méthode](../windows/ftmbase-marshalinterface-method.md)|Écrit dans un flux les données requises pour initialiser un objet proxy dans un processus client.|  
|[FtmBase::ReleaseMarshalData, méthode](../windows/ftmbase-releasemarshaldata-method.md)|Détruit un paquet de données marshalées.|  
|[FtmBase::UnmarshalInterface, méthode](../windows/ftmbase-unmarshalinterface-method.md)|Initialise un proxy nouvellement créé et retourne un pointeur d'interface vers ce proxy.|  
  
### Données membres publiques  
  
|Name|Description|  
|----------|-----------------|  
|[FtmBase::marshaller\_, données de membre](../windows/ftmbase-marshaller-data-member.md)|Contient une référence au marshaller libre de threads.|  
  
## Hiérarchie d'héritage  
 `FtmBase`  
  
## Configuration requise  
 **En\-tête:** ftm.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)
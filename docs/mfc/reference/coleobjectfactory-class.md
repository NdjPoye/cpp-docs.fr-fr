---
title: "COleObjectFactory Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleObjectFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class factories, COleObjectFactory class"
  - "COleObjectFactory class"
  - "création d'objet, objets OLE"
  - "objets (C++), créer des données OLE"
  - "OLE class factory"
  - "objets OLE"
  - "objets OLE, créer"
  - "OLE, class factory"
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleObjectFactory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente OLE fabrique de classe, qui crée des objets OLE tels que les serveurs, les objets Automation, et des documents.  
  
## Syntaxe  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleObjectFactory::COleObjectFactory](../Topic/COleObjectFactory::COleObjectFactory.md)|Construit un objet `COleObjectFactory`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleObjectFactory::GetClassID](../Topic/COleObjectFactory::GetClassID.md)|Retourne l'ID de classe OLE des objets que cette la fabrique crée.|  
|[COleObjectFactory::IsLicenseValid](../Topic/COleObjectFactory::IsLicenseValid.md)|Détermine si la licence du contrôle est valide.|  
|[COleObjectFactory::IsRegistered](../Topic/COleObjectFactory::IsRegistered.md)|Indique si la fabrique d'objet est enregistrée avec les DLL système OLE.|  
|[COleObjectFactory::Register](../Topic/COleObjectFactory::Register.md)|Stocke la fabrique d'objet avec les DLL système OLE.|  
|[COleObjectFactory::RegisterAll](../Topic/COleObjectFactory::RegisterAll.md)|Stocke les fabriques d'objet de toutes les applications avec les DLL système OLE.|  
|[COleObjectFactory::Revoke](../Topic/COleObjectFactory::Revoke.md)|Révoque l'inscription de la fabrique d'objet avec les DLL système OLE.|  
|[COleObjectFactory::RevokeAll](../Topic/COleObjectFactory::RevokeAll.md)|Révoque les inscriptions les fabriques d'objet d'une application avec les DLL système OLE.|  
|[COleObjectFactory::UnregisterAll](../Topic/COleObjectFactory::UnregisterAll.md)|Annule l'enregistrement de toutes les fabriques d'objet d'une application.|  
|[COleObjectFactory::UpdateRegistry](../Topic/COleObjectFactory::UpdateRegistry.md)|Stocke la fabrique d'objet avec le Registre système OLE.|  
|[COleObjectFactory::UpdateRegistryAll](../Topic/COleObjectFactory::UpdateRegistryAll.md)|Stocke les fabriques d'objet de toutes les applications avec le Registre système OLE.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[COleObjectFactory::GetLicenseKey](../Topic/COleObjectFactory::GetLicenseKey.md)|Demande une clé unique de la DLL du contrôle.|  
|[COleObjectFactory::OnCreateObject](../Topic/COleObjectFactory::OnCreateObject.md)|Appelé par l'infrastructure pour créer un objet du type de cette fabrique.|  
|[COleObjectFactory::VerifyLicenseKey](../Topic/COleObjectFactory::VerifyLicenseKey.md)|Vérifie que la clé incorporée dans le contrôle correspond à la clé incorporée dans le conteneur.|  
|[COleObjectFactory::VerifyUserLicense](../Topic/COleObjectFactory::VerifyUserLicense.md)|Vérifie que le contrôle est autorisé à utiliser au moment de le design.|  
  
## Notes  
 La classe d' `COleObjectFactory` a des fonctions membres pour exécuter les fonctions suivantes :  
  
-   Gérer l'inscription des objets.  
  
-   Mise à jour du OLE registre du système, ainsi que l'inscription à l'opération qui signale à OLE que les objets sont en cours de exécution et prêts à recevoir des messages.  
  
-   Appliquant l'attribution d'une licence en limitant l'utilisation du contrôle pour les développeurs autorisés au moment de le design et aux applications autorisées au moment de l'exécution.  
  
-   Stocker les fabriques d'objet contrôle avec le Registre système OLE.  
  
 Pour plus d'informations sur la création d'objets, consultez les articles [Objets de données et sources de données \(\) OLE](../../mfc/data-objects-and-data-sources-ole.md) et [objets de données et sources de données : Création et la destruction](../../mfc/data-objects-and-data-sources-creation-and-destruction.md).  Pour plus d'informations sur l'inscription, consultez l'article [Inscription](../../mfc/registration.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## Configuration requise  
 **Header:** afxdisp.h  
  
## Voir aussi  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)
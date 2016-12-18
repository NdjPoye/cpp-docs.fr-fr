---
title: "CRegKey Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRegKey"
  - "ATL::CRegKey"
  - "ATL.CRegKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Registre"
  - "CRegKey class"
  - "Registre, supprimer des clés"
  - "Registre, supprimer des valeurs"
  - "Registre, écrire dans"
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRegKey Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour manipuler des entrées dans la base de registres.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CRegKey  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRegKey::CRegKey](../Topic/CRegKey::CRegKey.md)|Constructeur.|  
|[CRegKey::~CRegKey](../Topic/CRegKey::~CRegKey.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRegKey::Attach](../Topic/CRegKey::Attach.md)|Appelez cette méthode pour attacher un HKEY à l'objet d' `CRegKey` en définissant le handle membre de [m\_hKey](../Topic/CRegKey::m_hKey.md) à `hKey`.|  
|[CRegKey::Close](../Topic/CRegKey::Close.md)|Appelez cette méthode pour libérer le handle membre de [m\_hKey](../Topic/CRegKey::m_hKey.md) et le définir la valeur NULL.|  
|[CRegKey::Create](../Topic/CRegKey::Create.md)|Appelez cette méthode pour créer la clé spécifiée, si elle n'existe pas comme valeur d' `hKeyParent`.|  
|[CRegKey::DeleteSubKey](../Topic/CRegKey::DeleteSubKey.md)|Appelez cette méthode pour supprimer la clé spécifiée du Registre.|  
|[CRegKey::DeleteValue](../Topic/CRegKey::DeleteValue.md)|Appelez cette méthode pour supprimer un champ de valeur de [m\_hKey](../Topic/CRegKey::m_hKey.md).|  
|[CRegKey::Detach](../Topic/CRegKey::Detach.md)|Appelez cette méthode pour détacher le handle membre de [m\_hKey](../Topic/CRegKey::m_hKey.md) de l'objet d' `CRegKey` et définissez `m_hKey` la valeur NULL.|  
|[CRegKey::EnumKey](../Topic/CRegKey::EnumKey.md)|Appelez cette méthode pour énumérer les sous\-clés de la clé de Registre ouverte.|  
|[CRegKey::Flush](../Topic/CRegKey::Flush.md)|Appelez cette méthode pour écrire tous les attributs de la clé de Registre ouverte dans le Registre.|  
|[CRegKey::GetKeySecurity](../Topic/CRegKey::GetKeySecurity.md)|Appelez cette méthode pour récupérer une copie du modèle de sécurité protégeant la clé de Registre ouverte.|  
|[CRegKey::NotifyChangeKeyValue](../Topic/CRegKey::NotifyChangeKeyValue.md)|Cette méthode signale l'appelant sur les modifications apportées aux attributs ou au contenu de la clé de Registre ouverte.|  
|[CRegKey::Open](../Topic/CRegKey::Open.md)|Appelez cette méthode pour ouvrir la clé spécifiée et définissez [m\_hKey](../Topic/CRegKey::m_hKey.md) au handle de cette clé.|  
|[CRegKey::QueryBinaryValue](../Topic/CRegKey::QueryBinaryValue.md)|Appelez cette méthode pour récupérer les données binaires d'un nom de valeur spécifiée.|  
|[CRegKey::QueryDWORDValue](../Topic/CRegKey::QueryDWORDValue.md)|Appelez cette méthode pour récupérer les données DWORD pour un nom de valeur spécifiée.|  
|[CRegKey::QueryGUIDValue](../Topic/CRegKey::QueryGUIDValue.md)|Appelez cette méthode pour récupérer les données du GUID pour le nom de la valeur spécifiée.|  
|[CRegKey::QueryMultiStringValue](../Topic/CRegKey::QueryMultiStringValue.md)|Appelez cette méthode pour récupérer les données à plusieurs chaînes pour un nom de valeur spécifiée.|  
|[CRegKey::QueryQWORDValue](../Topic/CRegKey::QueryQWORDValue.md)|Appelez cette méthode pour récupérer les données de QWORD pour un nom de valeur spécifiée.|  
|[CRegKey::QueryStringValue](../Topic/CRegKey::QueryStringValue.md)|Appelez cette méthode pour récupérer les données de chaîne pour le nom de la valeur spécifiée.|  
|[CRegKey::QueryValue](../Topic/CRegKey::QueryValue.md)|Appelez cette méthode pour récupérer les données du champ de valeur spécifié de [m\_hKey](../Topic/CRegKey::m_hKey.md).  Les versions antérieures de cette méthode sont plus prises en charge et ne sont marquées comme **ATL\_DEPRECATED**.|  
|[CRegKey::RecurseDeleteKey](../Topic/CRegKey::RecurseDeleteKey.md)|Appelez cette méthode pour supprimer la clé spécifiée du Registre et pour supprimer explicitement toutes les sous\-clés.|  
|[CRegKey::SetBinaryValue](../Topic/CRegKey::SetBinaryValue.md)|Appelez cette méthode pour définir la valeur binaire de la clé de Registre.|  
|[CRegKey::SetDWORDValue](../Topic/CRegKey::SetDWORDValue.md)|Appelez cette méthode pour définir la valeur DWORD de la clé de Registre.|  
|[CRegKey::SetGUIDValue](../Topic/CRegKey::SetGUIDValue.md)|Appelez cette méthode pour définir la valeur GUID de la clé de Registre.|  
|[CRegKey::SetKeySecurity](../Topic/CRegKey::SetKeySecurity.md)|Appelez cette méthode pour définir la sécurité de la clé de Registre.|  
|[CRegKey::SetKeyValue](../Topic/CRegKey::SetKeyValue.md)|Appelez cette méthode pour enregistrer des données dans un domaine spécifié de valeur d'une clé spécifiée.|  
|[CRegKey::SetMultiStringValue](../Topic/CRegKey::SetMultiStringValue.md)|Appelez cette méthode pour affecter la valeur à plusieurs chaînes de la clé de Registre.|  
|[CRegKey::SetQWORDValue](../Topic/CRegKey::SetQWORDValue.md)|Appelez cette méthode pour définir la valeur de QWORD de la clé de Registre.|  
|[CRegKey::SetStringValue](../Topic/CRegKey::SetStringValue.md)|Appelez cette méthode pour définir la valeur de chaîne de la clé de Registre.|  
|[CRegKey::SetValue](../Topic/CRegKey::SetValue.md)|Appelez cette méthode pour enregistrer des données dans le domaine de valeur spécifié de [m\_hKey](../Topic/CRegKey::m_hKey.md).  Les versions antérieures de cette méthode sont plus prises en charge et ne sont marquées comme **ATL\_DEPRECATED**.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRegKey::operator HKEY](../Topic/CRegKey::operator%20HKEY.md)|Convertit un objet d' `CRegKey` à un HKEY.|  
|[CRegKey::operator \=](../Topic/CRegKey::operator%20=.md)|Opérateur d'assignation|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRegKey::m\_hKey](../Topic/CRegKey::m_hKey.md)|Contient un handle de la clé de Registre associé à l'objet d' `CRegKey` .|  
|[CRegKey::m\_pTM](../Topic/CRegKey::m_pTM.md)|Pointeur vers l'objet d' `CAtlTransactionManager`|  
  
## Notes  
 `CRegKey` fournit des méthodes pour créer et touches et valeurs d'effacement dans la base de registres.  Le Registre contient un jeu d'installation\- spécifique de définitions pour les composants système, tels que les numéros de version du logiciel, des mappages de logique\-à\- physique de matériel installé, et des objets COM.  
  
 `CRegKey` fournit une interface de programmation à la base de registres pour un ordinateur donné.  Par exemple, pour ouvrir une clé de Registre spécifique, appelez `CRegKey::Open`.  Pour récupérer ou modifier une valeur de données, un appel `CRegKey::QueryValue` ou un `CRegKey::SetValue`, respectivement.  Pour fermer une clé, appelez `CRegKey::Close`.  
  
 Lorsque vous fermez une clé, ses données du Registre sont écrites \(vidé\) sur le disque dur.  Ce processus peut prendre quelques secondes.  Si votre application doit explicitement écrire des données de Registre sur le disque dur, vous pouvez appeler la fonction de [RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) Win32.  Toutefois, **RegFlushKey** utilise beaucoup de ressources système et doit être appelé uniquement si absolument nécessaire.  
  
> [!IMPORTANT]
>  Toutes les méthodes qui permettent à l'appelant de spécifier un emplacement de Registre ont la possibilité de lire les données qui ne peuvent pas être de confiance.  Les méthodes qui se servent de [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) doivent prendre en compte que cette fonction ne gère pas explicitement les chaînes qui sont NULL terminées.  Les deux conditions doivent être examinées pour rechercher par le code appelant.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Exemple DCOM](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Registry Overview](http://msdn.microsoft.com/library/windows/desktop/ms724871)   
 [Registry Functions](http://msdn.microsoft.com/library/windows/desktop/ms724875)   
 [Registry Value Types](http://msdn.microsoft.com/library/windows/desktop/ms724884)
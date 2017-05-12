---
title: "Platform::Agile, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile"
ms.assetid: e34459a9-c429-4c79-97fd-030c43ca4155
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Agile, classe
Représente un objet qui a MashalingBehavior\=Standard en tant qu’objet agile, ce qui réduit considérablement les risques d’exception de thread d’exécution.`Agile<T>` permet à l’objet non agile d’appeler ou d’être appelé par le même thread ou un thread différent. Pour plus d'informations, consultez [Thread et Marshaling](../cppcx/threading-and-marshaling-c-cx.md).  
  
## Syntaxe  
  
```scr  
  
template <typename T>  
    class Agile  
;  
```  
  
#### Paramètres  
 T  
 Nom de type de la classe non agile.  
  
## Notes  
 La plupart des classes de [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] sont agiles. Un objet agile peut appeler, ou être appelé par, un objet intra\-processus ou hors processus dans le même thread ou un autre thread. Si un objet n’est pas agile, encapsulez l’objet non agile dans un objet `Agile<T>` agile. L’objet `Agile<T>` peut ensuite être marshalé, et l’objet non agile sous\-jacent peut être utilisé.  
  
 La classe `Agile<T>` est une classe C\+\+ native standard qui nécessite `agile.h`. Elle représente l’objet non agile et le *contexte* de l’objet Agile. Le contexte spécifie le modèle de thread et le comportement de marshaling d’un objet agile. Le système d’exploitation utilise le contexte pour déterminer comment marshaler un objet.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[Agile::Agile, constructeur](../cppcx/agile-agile-constructor.md)|Initialise une nouvelle instance de la classe Agile.|  
|[Agile::~Agile, destructeur](../cppcx/agile-tilde-agile-destructor.md)|Détruit l'instance actuelle de la classe Agile.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[Agile::Get](../cppcx/agile-get-method.md)|Retourne un handle vers l’objet représenté par l’objet Agile actif.|  
|[Agile::GetAddressOf](../cppcx/agile-getaddressof-method.md)|Réinitialise l’objet Agile actif, puis retourne l’adresse d’un handle vers un objet de type `T`.|  
|[Agile::GetAddressOfForInOut](../cppcx/agile-getaddressofforinout-method.md)|Retourne l'adresse d'un handle vers l'objet représenté par l'objet Agile actif.|  
|[Agile::Release](../cppcx/agile-release-method.md)|Ignore l'objet et le contexte sous\-jacent de l'objet Agile actif.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[Agile::operator\-\>](../cppcx/agile-operator-arrow-operator.md)|Récupère un handle vers l’objet représenté par l’objet Agile actif.|  
|[Agile::operator\=](../cppcx/agile-operator-assign-operator.md)|Assigne la valeur spécifiée à l’objet Agile actif.|  
  
## Hiérarchie d'héritage  
 `Object`  
  
 `Agile`  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête :** agile.h  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)
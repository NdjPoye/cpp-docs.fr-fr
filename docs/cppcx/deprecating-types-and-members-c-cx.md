---
title: "D&#233;conseiller des types et des membres (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# D&#233;conseiller des types et des membres (C++/CX)
En C\+\+\/CX, le fait de déconseiller les types et membres [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] pour les producteurs et les consommateurs à l'aide de l'attribut [Deprecated](http://msdn.microsoft.com/fr-fr/8b02ad36-3b5f-4361-888b-e6a99040e57c) est pris en charge. Si vous consommez une API à laquelle cet attribut a été appliqué, vous recevez un message d'avertissement au moment de la compilation qui indique que l'API est déconseillée et recommande l'utilisation d'une autre API. Dans vos propres types et méthodes publics, vous pouvez appliquer cet attribut et fournir votre message personnalisé.  
  
> [!CAUTION]
>  L'attribut [Deprecated](http://msdn.microsoft.com/fr-fr/8b02ad36-3b5f-4361-888b-e6a99040e57c) doit être utilisé uniquement avec les types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Pour les classes et les membres C\+\+ standard, utilisez [\_\_declspec\(deprecated\)](http://msdn.microsoft.com/library/044swk7y.aspx).  
  
## Exemple  
 L'exemple suivant montre comment déconseiller vos propres API publiques, par exemple dans un composant Windows Runtime. Le deuxième paramètre, de type [Windows:Foundation::Metadata::DeprecationType](http://msdn.microsoft.com/fr-fr/ee01e63d-37d0-4273-accc-fca174f88bfa), spécifie si l'API est déconseillée ou supprimée. Actuellement, seule la valeur DeprecationType::Deprecated est prise en charge. Le troisième paramètre de l'attribut spécifie le [Windows::Foundation::Metadata::Platform](http://msdn.microsoft.com/fr-fr/1eae292d-1ab7-4d97-a58c-b0beffd51ef5) auquel l'attribut s'applique.  
  
```  
  
namespace wfm = Windows::Foundation::Metadata; public ref class Bicycle sealed { public: property double Speed; [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)] double ComputeAngularVelocity(); };  
```  
  
## Cibles prises en charge  
 Le tableau suivant répertorie les constructions auxquelles l'attribut Deprecated peut être appliqué :  
  
||  
|-|  
|Contrôle XAML|  
|délégué|  
|événement|  
|champ enum|  
|enum|  
|struct|  
|méthode|  
|classe|  
|interface|  
|propriété|  
|champ struct|  
|constructeur paramétrable|  
  
## Voir aussi  
 [système de type](../cppcx/type-system-c-cx.md)   
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)
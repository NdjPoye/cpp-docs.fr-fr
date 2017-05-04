---
title: "Int&#233;gration&#160;CLR (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# Int&#233;gration&#160;CLR (C++/CX)
Certains types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] reçoivent un traitement spécial en [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] et les langages basés sur le Common Language Runtime \(CLR\). Cet article décrit comment plusieurs types dans un langage sont mappés à un autre langage. Par exemple, le CLR mappe Windows.Foundation.IVector à System.Collections.IList, Windows.Foundation.IMap à System.Collections.IDictionary, et ainsi de suite. De même, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] mappe spécialement des types tels que Platform::Delegate et Platform::String.  
  
## Mappage du [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] à [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 Lorsque [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] lit un fichier de métadonnées Windows \(.winmd\), le compilateur mappe automatiquement les espaces de noms et les types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] communs aux espaces de noms et aux types [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]. Par exemple, le type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] numérique `UInt32` est automatiquement mappé à `default::uint32`.  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] mappe plusieurs autres types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] à l’espace de noms **Platform**. Par exemple, le handle HSTRING **Windows::Foundation**, qui représente une chaîne Unicode en lecture seule, est mappé à la classe [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]`Platform::String`.  Lorsqu’une opération [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] retourne une erreur HRESULT, elle est mappée à un [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] `Platform::Exception`.  Pour plus d'informations, consultez [Built\-in Types](http://msdn.microsoft.com/fr-fr/acc196fd-09da-4882-b554-6c94685ec75f).  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] mappe également certains types dans les espaces de noms [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] pour améliorer les fonctionnalités du type. Pour ces types, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] fournit des constructeurs d’assistance et des méthodes qui sont propres à C\+\+ et ne sont pas disponibles dans le fichier .winmd standard du type.  
  
 Les listes suivantes présentent les structs de valeurs qui prennent en charge les nouvelles méthodes d’assistance et les nouveaux constructeurs. Si vous avez déjà écrit du code qui utilise des listes d’initialisation de struct, modifiez\-le pour utiliser les constructeurs qui viennent d’être ajoutés.  
  
 **Windows::Foundation**  
  
-   Point  
  
-   Rect  
  
-   Size  
  
 **Windows::UI**  
  
-   Color  
  
 **Windows::UI::Xaml**  
  
-   CornerRadius  
  
-   Duration  
  
-   GridLength  
  
-   Thickness  
  
 **Windows::UI::Xaml::Interop**  
  
1.  TypeName  
  
 **Windows::UI::Xaml::Media**  
  
-   Matrix  
  
 **Windows::UI::Xaml::Media::Animation**  
  
-   KeyTime  
  
-   RepeatBehavior  
  
 **Windows::UI::Xaml::Media::Media3D**  
  
-   Matrix3D  
  
## Mappage du CLR à [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 Lorsque les compilateurs Visual C\+\+ ou C\# lisent un fichier .winmd, ils mappent automatiquement certains types dans le fichier de métadonnées aux types [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] ou CLR appropriés. Par exemple, dans le CLR, l’interface IVector\<T\>  est mappée à IList\<T\>. En revanche, en [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], l’interface IVector\<T\> n’est pas mappée à un autre type.  
  
 IReference\<T\> dans le [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] est mappée à Nullable\<T\> dans .NET.  
  
## Voir aussi  
 [Interopérabilité avec d'autres langages](../cppcx/interoperating-with-other-languages-c-cx.md)
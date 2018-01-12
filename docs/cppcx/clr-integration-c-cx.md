---
title: "Intégration du CLR (C + c++ / CX) | Documents Microsoft"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9851a7aa0d1dad84a37504b479c551ffa63bcf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="clr-integration-ccx"></a>Intégration CLR (C++/CX)
Certains types Windows Runtime reçoivent un traitement spécial dans C + c++ / CX et les langues qui sont basées sur le common language runtime (CLR). Cet article décrit comment plusieurs types dans un langage sont mappés à un autre langage. Par exemple, le CLR mappe Windows.Foundation.IVector à System.Collections.IList, Windows.Foundation.IMap à System.Collections.IDictionary, et ainsi de suite. De même, C + c++ / CX mappe spécialement des types tels que Platform::Delegate et Platform::String.  
  
## <a name="mapping-the-windows-runtime-to-ccx"></a>Mappage de Windows Runtime C + c++ / CX  
 Lorsque C + c++ / CX lit un fichier de métadonnées (.winmd) de Windows, le compilateur mappe automatiquement les types et les espaces de noms communs Windows Runtime C + c++ / CX espaces de noms et les types. Par exemple, le type Windows Runtime numérique `UInt32` est automatiquement mappé à `default::uint32`.  
  
 C + c++ / CX mappe plusieurs autres types Windows Runtime pour le **plateforme** espace de noms. Par exemple, le **Windows::Foundation** handle HSTRING, qui représente une chaîne de texte Unicode en lecture seule, est mappé à C + c++ / CX `Platform::String` classe. Lorsqu’une opération de Windows Runtime retourne une erreur HRESULT, il est mappé à un C + c++ / CX `Platform::Exception`. Pour plus d'informations, consultez [Built-in Types](http://msdn.microsoft.com/en-us/acc196fd-09da-4882-b554-6c94685ec75f).  
  
 C + c++ / CX mappe également certains types dans les espaces de noms Windows Runtime pour améliorer les fonctionnalités du type. Pour ces types, C + c++ / CX fournit des constructeurs d’assistance et les méthodes qui sont spécifiques à C++ et ne sont pas disponibles dans le fichier de .winmd standard du type.  
  
 Les listes suivantes présentent les structs de valeurs qui prennent en charge les nouvelles méthodes d’assistance et les nouveaux constructeurs. Si vous avez déjà écrit du code qui utilise des listes d’initialisation de struct, modifiez-le pour utiliser les constructeurs qui viennent d’être ajoutés.  
  
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
  
## <a name="mapping-the-clr-to-ccx"></a>Mappage du CLR à C + c++ / CX  
 Lorsque les compilateurs Visual C++ ou c# lisent un fichier .winmd, ils mappent automatiquement certains types dans le fichier de métadonnées appropriées C + c++ / CX ou CLR types. Par exemple, dans le CLR, le IVector\<T > interface est mappée à IList\<T >. Mais en langage c++ / CX, le IVector\<T > interface n’est pas mappé à un autre type.  
  
 IReference\<T > dans le Windows Runtime est mappée à Nullable\<T > dans .NET.  
  
## <a name="see-also"></a>Voir aussi  
 [Interopérabilité avec d’autres langages](../cppcx/interoperating-with-other-languages-c-cx.md)
---
title: Array et WriteOnlyArray (C + c++ / CX) | Documents Microsoft
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47c26ef4058cc3116d964740a93f7395c300b92b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="array-and-writeonlyarray-ccx"></a>Array et WriteOnlyArray (C++/CX)
Vous pouvez utiliser librement des tableaux de style C normaux ou [std::array](../standard-library/array-class-stl.md) dans C + c++ / programme CX (bien que [std::vector](../standard-library/vector-class.md) est souvent un meilleur choix), mais dans toute API qui est publié dans les métadonnées, vous devez convertir un tableau de style C ou de vecteur à un [Platform::Array](../cppcx/platform-array-class.md) ou [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) type en fonction de son utilisation. Le type [Platform::Array](../cppcx/platform-array-class.md) n'est pas aussi efficace ni aussi puissant que le type [std::vector](../standard-library/vector-class.md), donc en règle générale, vous devez éviter de l'utiliser dans le code interne qui exécute un grand nombre d'opérations sur les éléments de tableau.  
  
 Les types de tableau suivants peuvent être passés à travers l'ABI :  
  
1.  const Platform::Array^  
  
2.  Platform::Array^*  
  
3.  Platform::WriteOnlyArray  
  
4.  valeur de retour de Platform::Array^  
  
 Vous utilisez ces types de tableau pour implémenter les trois types de modèles de tableau sont définis par le Windows Runtime.  
  
 PassArray  
 Utilisé lorsque l'appelant passe un tableau à une méthode. Le type de paramètre d’entrée C++ est `const` [Platform::Array](../cppcx/platform-array-class.md)\<T >.  
  
 FillArray  
 Utilisé lorsque l'appelant passe un tableau à remplir par la méthode. Le type de paramètre d’entrée C++ est [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)\<T >.  
  
 ReceiveArray  
 Utilisé lorsque l'appelant reçoit un tableau que la méthode alloue. En langage C++/CX, vous pouvez retourner un tableau en valeur de retour comme un Array^, ou vous pouvez le retourner comme paramètre de sortie de type Array^*.  
  
## <a name="passarray-pattern"></a>Modèle PassArray  
 Lorsque le code client passe un tableau à une méthode C++ et que la méthode ne le modifie pas, la méthode accepte le tableau comme constante Array^. Au niveau des applications Windows Runtime interface binaire (ABI), cela s’appelle un PassArray. L'exemple ci-dessous montre comment passer un tableau alloué en JavaScript à la fonction C++ qui le lit.  
  
 [!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]  
  
 L'extrait de code suivant illustre la méthode C++ :  
  
 [!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]  
  
## <a name="receivearray-pattern"></a>Modèle ReceiveArray  
 Dans le modèle ReceiveArray, le code client déclare un tableau et le passe à une méthode qui lui alloue de la mémoire et l'initialise. Le type de paramètre d'entrée C++ est un pointeur chapeau : `Array<T>^*`. L'exemple suivant indique comment déclarer un objet tableau dans JavaScript et le passer à une fonction C++ qui alloue de la mémoire, initialise les éléments et le retourne à JavaScript. JavaScript traite le tableau alloué comme une valeur de retour, mais la fonction C++ le traite comme un paramètre de sortie.  
  
 [!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]  
  
 L'extrait de code suivant montre deux façons d'implémenter la méthode C++ :  
  
 [!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]  
  
## <a name="fill-arrays"></a>Remplir les tableaux  
 Lorsque vous souhaitez allouer un tableau dans l'appelant et l'initialiser ou le modifier dans l'appelé, utilisez `WriteOnlyArray`. L'exemple ci-dessous indique comment implémenter une fonction c++ qui utilise `WriteOnlyArray` et l'appelle à partir de JavaScript.  
  
 [!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]  
  
 L'extrait de code suivant montre comment implémenter la méthode C++ :  
  
 [!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]  
  
## <a name="array-conversions"></a>Conversions de tableau  
 L'exemple ci-dessous montre comment utiliser un objet [Platform::Array](../cppcx/platform-array-class.md) pour construire d'autres types de collections :  
  
 [!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]  
  
 L'exemple ci-dessous montre comment construire un objet [Platform::Array](../cppcx/platform-array-class.md) à partir d'un tableau de style C et le retourner à partir d'une méthode publique.  
  
 [!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]  
  
## <a name="jagged-arrays"></a>Tableaux en escalier  
 Le système de types Windows Runtime ne prend pas en charge le concept des tableaux en escalier et vous ne pouvez pas donc pas utiliser `IVector<Platform::Array<T>>` comme valeur de retour ou paramètre de méthode dans une méthode publique. Pour passer un tableau en escalier ou une séquence de séquences à travers l'ABI, utilisez `IVector<IVector<T>^>`.  
  
## <a name="use-arrayreference-to-avoid-copying-data"></a>Utilisez le type ArrayReference pour éviter de copier les données.  
 Dans certains scénarios où les données sont passées à travers l'ABI dans un [Platform::Array](../cppcx/platform-array-class.md)et où vous voulez finalement traiter ces données dans un tableau de style C pour plus d'efficacité, vous pouvez utiliser [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) pour éviter l'opération de copie supplémentaire. Lorsque vous passez un type [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) comme argument à un paramètre qui accepte un `Platform::Array`, le `ArrayReference` stocke les données directement dans un tableau de style C que vous spécifiez. Gardez à l'esprit que le type `ArrayReference` ne peut effectuer aucun verrouillage sur les données sources. Ainsi, si ces données sont modifiées ou supprimées sur un autre thread avant l'appel, les résultats seront non définis.  
  
 L’extrait de code suivant montre comment copier les résultats d’une opération [DataReader](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.datareader.aspx) dans un `Platform::Array` (le modèle habituel), puis comment substituer `ArrayReference` pour copier les données directement dans un tableau de style C :  
  
 [!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]  
  
## <a name="avoid-exposing-an-array-as-a-property"></a>Évitez d'exposer un tableau comme propriété  
 En général, vous devez éviter d'exposer un type `Platform::Array` en tant que propriété dans une classe ref, car le tableau entier est retourné même si le code client tente uniquement d'accéder à un seul élément. Quand vous devez exposer un conteneur de séquence en tant que propriété dans une classe ref publique, choisissez plutôt [Windows::Foundation::IVector](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) . Dans les API privées ou internes (qui ne sont pas publiées en métadonnées), envisagez d'utiliser un conteneur C++ standard tel que le type [std::vector](../standard-library/vector-class.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Système de type](../cppcx/type-system-c-cx.md)   
 [Référence du langage Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence des espaces de noms](../cppcx/namespaces-reference-c-cx.md)
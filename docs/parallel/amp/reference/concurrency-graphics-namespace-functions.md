---
title: "Fonctions d’espace de noms Concurrency::Graphics | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ace01cd5-29d3-4356-930e-c81a61c5f934
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1c17becb6bc3fb9b243a65652bf019b7fad1b8cd
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencygraphics-namespace-functions"></a>Fonctions d’espace de noms Concurrency::Graphics
|||  
|-|-|  
|[Copy, fonction (Concurrency::graphics Namespace)](#copy)|[copy_async, fonction (Concurrency::graphics Namespace)](#copy_async)|  
  
##  <a name="a-namecopya--copy-function-concurrencygraphics-namespace"></a><a name="copy"></a>Copy, fonction (Concurrency::graphics Namespace)  
 Copie d’une texture source dans un mémoire tampon de destination, ou copie d’une mémoire tampon source dans un mémoire tampon de destination. La forme générale de cette fonction est `copy(src, dest)`.  
  
```  
template <
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type>  
>  
void copy (
    const _Src_type& _Src,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
void copy(
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(
    const void* _Src,  
    unsigned int _Src_byte_size,  
    _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(InputIterator first, InputIterator last, _Dst_type& _Dst);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>void copy(InputIterator first, InputIterator last, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
void copy(
    const _Src_type& _Src, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
void copy (
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy (
    const _Src_type& _Src, _Dst_type& _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture,  
    void>::type 
>  
void copy (
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Src_type::rank>& _Copy_extent);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Copy_extent`  
 L’étendue de la section de texture à copier.  
  
 `_Dst`  
 L’objet de destination.  
  
 `_Dst_byte_size`  
 Le nombre d’octets dans la destination.  
  
 `_Dst_type`  
 Le type de l’objet de destination.  
  
 `_Dst_offset`  
 Offset dans la destination à partir duquel commencer la copie.  
  
 `InputIterator`  
 Le type de l’entrée interator.  
  
 `OutputIterator`  
 Le type de l’itérateur de sortie.  
  
 `_Src`  
 Pour l’objet à copier.  
  
 `_Src_byte_size`  
 Le nombre d’octets dans la source.  
  
 `_Src_type`  
 Le type de l’objet source.  
  
 `_Src_offset`  
 Offset dans la source à partir duquel commencer la copie.  
  
 `first`  
 Un itérateur de début dans le conteneur source.  
  
 `last`  
 Un itérateur de fin dans le conteneur source.  
  
##  <a name="a-namecopyasynca--copyasync-function-concurrencygraphics-namespace"></a><a name="copy_async"></a>copy_async, fonction (Concurrency::graphics Namespace)  
 Copie de manière asynchrone une texture source dans une mémoire tampon de destination, ou copie d’une mémoire tampon source dans un mémoire tampon de destination et renvoie un [completion_future](completion-future-class.md) objet qui peut être attendu. Impossible de copier les données lorsque le code s’exécute sur un accélérateur. La forme générale de cette fonction est `copy(src, dest)`.  
  
```  
template<
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const _Src_type& _Src,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template<
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src, _Dst_type& _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset, _Dst_type &_Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Src_type::rank>& _Copy_extent);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Copy_extent`  
 L’étendue de la section de texture à copier.  
  
 `_Dst`  
 L’objet de destination.  
  
 `_Dst_byte_size`  
 Le nombre d’octets dans la destination.  
  
 `_Dst_type`  
 Le type de l’objet de destination.  
  
 `_Dst_offset`  
 Offset dans la destination à partir duquel commencer la copie.  
  
 `InputIterator`  
 Le type de l’entrée interator.  
  
 `OutputIterator`  
 Le type de l’itérateur de sortie.  
  
 `_Src`  
 Pour l’objet à copier.  
  
 `_Src_byte_size`  
 Le nombre d’octets dans la source.  
  
 `_Src_type`  
 Le type de l’objet source.  
  
 `_Src_offset`  
 Offset dans la source à partir duquel commencer la copie.  
  
 `first`  
 Un itérateur de début dans le conteneur source.  
  
 `last`  
 Un itérateur de fin dans le conteneur source.  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)


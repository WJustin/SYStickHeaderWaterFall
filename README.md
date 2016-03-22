SYStickHeaderWaterFall 中文介绍
==============
[![License MIT](https://img.shields.io/badge/license-MIT-green.svg?style=flat)](https://raw.githubusercontent.com/zhangsuya/SYStickHeaderWaterFall/master/LICENSE)&nbsp;
[![CocoaPods](http://img.shields.io/cocoapods/v/SYStickHeaderWaterFall.svg?style=flat)](http://cocoapods.org/?q= SYStickHeaderWaterFall)&nbsp;
[![CocoaPods](http://img.shields.io/cocoapods/p/SYStickHeaderWaterFall.svg?style=flat)](http://cocoapods.org/?q= SYStickHeaderWaterFall)&nbsp;
[![Support](https://img.shields.io/badge/support-iOS%208%2B%20-blue.svg?style=flat)](https://www.apple.com/nl/ios/)&nbsp;


灵活支持各种类型的瀑布流结构，喜欢就star一下吧。

![image](https://github.com/zhangsuya/SYStickHeaderWaterFall/blob/master/SYStickHeaderWaterFall/4.gif)

以后封装任务：
1.装饰视图的增加。

安装
==============

### CocoaPods

1. 将 cocoapods 更新至最新版本.
2. 在 Podfile 中添加 `pod "SYStickHeaderWaterFall"`。
3. 执行 `pod install` 或 `pod update`。

用法
==============
1. 初始化并设置delegate：
SYStickHeaderWaterFallLayout *cvLayout = [[SYStickHeaderWaterFallLayout alloc] init];
cvLayout.delegate = self;


2. 设置属性：
 //是否设置sectionHeader停留,默认YES
    cvLayout.isStickyHeader = YES;
//section停留的位置是否包括原来设置的top，默认NO
    cvLayout.isTopForHeader = YES;
//在此修正sectionheader停留的位置,默认64
  cvLayout.fixTop = 64.0f;
3. 实现代理方法：
/**
 *  返回所在section的每个item的width（一个section只有一个width）
 *
 */
- (CGFloat)collectionView:(nonnull UICollectionView *)collectionView
                   layout:(nonnull SYStickHeaderWaterFallLayout *)collectionViewLayout
   widthForItemInSection:( NSInteger )section;
/**
 *  返回所在indexPath的每个item的height（每个item有一个height，要不然怎么是瀑布流😄）
 *
 */
- (CGFloat)collectionView:(nonnull UICollectionView *)collectionView
                   layout:(nonnull SYStickHeaderWaterFallLayout *)collectionViewLayout
 heightForItemAtIndexPath:(nonnull NSIndexPath *)indexPath;

@optional
/**
 *  返回所在indexPath的header的height
 *
*/
- (CGFloat) collectionView:(nonnull UICollectionView *)collectionView
                    layout:(nonnull SYStickHeaderWaterFallLayout *)collectionViewLayout
heightForHeaderAtIndexPath:(nonnull NSIndexPath *)indexPath;
/**
 *  返回所在section与上一个section的间距(表达的可能不够准确，但是你们都懂的)
 *
 */
- (CGFloat) collectionView:(nonnull UICollectionView *)collectionView
                    layout:(nonnull SYStickHeaderWaterFallLayout *)collectionViewLayout
topInSection:(NSInteger )section;
/**
 *  返回所在section与下一个section的间距(表达的可能不够准确，但是你们都懂的)
 *
 */
- (CGFloat) collectionView:(nonnull UICollectionView *)collectionView
                    layout:(nonnull SYStickHeaderWaterFallLayout *)collectionViewLayout
            bottomInSection:( NSInteger)section;
/**
 *  返回所在section的header停留时与顶部的距离（如果设置isTopForHeader ＝ yes ，则距离会叠加）
 *
 */
- (CGFloat) collectionView:(nonnull UICollectionView *)collectionView
                    layout:(nonnull SYStickHeaderWaterFallLayout *)collectionViewLayout
           headerToTopInSection:( NSInteger)section;

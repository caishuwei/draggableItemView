# draggableItemView
自定义ListView/GridView实现Item拖拽重排序

## 使用案例



```
//必须使用此方法设置拖拽处理对象
//一下是通用实现
gv_animation.setDragChangeHandler(new IDragChangeHandler() {

            @Override
            public Object getItemDataByPos(int position) {
                return adapter.getItem(position);
            }

            @Override
            public void onDragPosChange(int oldPos, int newPos) {
                GridItem item = listData.remove(oldPos);
                listData.add(newPos, item);
                adapter.notifyDataSetChanged();
            }
        });
```


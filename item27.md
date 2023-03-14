item 27 의 instanceOf()연산자를 사용하는 방법을 고려해 보았습니다

## 기존 @SuppressWarnings("unchecked")적용

```
public class TestToArray {
    private int size;
    private Object[] elements;
    public <T> T[] toArray(T[] a){
        if(a.length < size){
            //생성한 배열과 매개변수로 받은 배열의 타입이 모두 T[] 로 같으므로
            // 올바른 형변환이다
            @SuppressWarnings("unchecked")
            T[] result = (T[]) Arrays.copyOf(elements, size, a.getClass());
            return result;
        }
        System.arraycopy(elements,0,a,0,size);
        if (a.length > size)
            a[size] = null;
        return a;
    }
}
```
## instanceOf()연산자를 사용하는 방법을 고려해 보았습니다

```
public <T> T[] toArray(T[] a){
    if(a == null) {
        throw new NullPointerException();
    }
    
    if(a.length < size){
        // 생성한 배열과 매개변수로 받은 배열의 타입이 모두 T[] 로 같으므로
        // 올바른 형변환이다
        if(a.getClass().isInstance(elements)) {
            return Arrays.copyOf(elements, size, (Class<? extends T[]>) a.getClass());
        } else {
            T[] result = (T[]) Array.newInstance(a.getClass().getComponentType(), size);
            System.arraycopy(elements, 0, result, 0, size);
            return result;
        }
    }
    
    System.arraycopy(elements, 0, a, 0, size);
    
    if (a.length > size)
        a[size] = null;
    
    return a;
}
```
instanceof 연산자는 a와 elements의 클래스가 같은지를 확인하여, 해당하는 조건에 맞는 형변환을 수행하는 데 사용됩니다.

좋은 방안이 있다면 같이 생각하고 공유하고 싶습니다 🧐 

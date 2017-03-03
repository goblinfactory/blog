## And the award for most under-appreciated friend goes to ...

***`IEnumerable.GetEnumerator()`***

Just for fun, here's some code showing extending Linq with your own custom methods does not have to be scary.

`IEnumerable`, `GetEnumerator` and `yield` are your friends and are super performant. 

```csharp

	public static class MyLinqExtensions
	{
		public static IEnumerable<int> RoundRobin(this IEnumerable<int> a, IEnumerable<int> b)
		{
			var ae = a.GetEnumerator();
			var be = b.GetEnumerator();
	
			bool aHasNumber = ae.MoveNext();
			bool bHasNumber = be.MoveNext();
	
			while (aHasNumber || bHasNumber)
			{
				if (aHasNumber)
				{
					yield return ae.Current;
					aHasNumber = ae.MoveNext();
				}
	
				if (bHasNumber)
				{
					yield return be.Current;
					bHasNumber = be.MoveNext();
				}
			}
		}
	}
	void Main()
	{
		var arr1 = new[] { 1, 2, 3, 4 };
		var arr2 = new[] { 4, 5, 6 };
		var arr3 = new[] { 7, 8, 9};
		var arr4 = new int[] {  };
		
		// arrays the same size
		Assert.AreEqual(new[] { 4, 7, 5, 8, 6, 9 }, arr2.RoundRobin(arr3).ToArray());
		
		// array 1 bigger than array 2
		Assert.AreEqual(new[] { 1, 4, 2, 5, 3, 6, 4 }, arr1.RoundRobin(arr2).ToArray());
	
		// array 1 smaller than 2
		Assert.AreEqual(new[] { 4, 1, 5, 2, 6, 3, 4 }, arr2.RoundRobin(arr1).ToArray());
	
		// 2 empty, 1 not
		Assert.AreEqual(new[] { 4, 5, 6 }, arr2.RoundRobin(new int[] { }).ToArray());
		
		// 1 empty, 2 not
		Assert.AreEqual(new[] { 1, 2, 3, 4 }, arr1.RoundRobin(new int[] { }).ToArray());
	
		// both empty
		Assert.AreEqual(new int[] {  }, arr4.RoundRobin(arr4).ToArray());
	
		// prove it's Linq! mmm Might make an interesting interview question, discuss why this is or is not a good proof?
		Assert.AreEqual(new[] { 1, 7, 2, 8, 3}, AllPositiveLongNumbers().RoundRobin(arr3).Take(5).ToArray());
		Assert.AreEqual(3,howBigDidWeGet);
		
		Console.WriteLine("pass");
	}
	
	static int howBigDidWeGet = 0;
	public IEnumerable<int> AllPositiveLongNumbers()
	{
		while(true)	yield return ++howBigDidWeGet;
	}
	
	static int howBigDidWeGet = 1;
	public IEnumerable<int> AllPositiveLongNumbers()
	{
		yield return howBigDidWeGet++;
	}






```

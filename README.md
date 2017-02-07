# HelloWorld

Scanner sc = new Scanner(System.in);
		int count = sc.nextInt();
		ArrayList<Integer> sticks = new ArrayList<Integer>();
		int min = Integer.MAX_VALUE;
		
		for(int i = 0;i < count; i++){
			
			int n = sc.nextInt();
			if(n < min)
				min = n;
			sticks.add(n);
		}
		int localMin = min;
		while(!sticks.isEmpty()){
			
			System.out.println(count);
			ArrayList<Integer> buf = new ArrayList<Integer>();
		
			for(int len : sticks){
				int n = len - min;
				
				if(n > 0){
				  buf.add(n);
				  if(n < localMin)
					localMin = n;
				}
			}
			
			min = localMin;
			count = buf.size();
			sticks.clear();
			sticks.addAll(buf);
		}
		

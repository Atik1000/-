### ৩. [সার্চিং এলগোরিদম 🔍](algorithms/searching.md)

- **লিনিয়ার সার্চ**: এক এক করে খোঁজা (যেমন বইয়ের পাতা উল্টানো)  
  "বইয়ের প্রতিটা পাতা এক এক করে উল্টাতে উল্টাতে খুঁজে বের করলেন। কি প্যাসেন্ট! কিন্তু কি সহজ।"
  
  **Pseudocode**:
  ```python
  def linear_search(arr, target):  # Changed 'list' to 'arr' as list is a reserved keyword
      for i in range(len(arr)):
          if arr[i] == target:
              return i  # Found it!
      return -1  # Not found
  ```

- **বাইনারি সার্চ**: মাঝখান থেকে খোঁজা (ডিকশনারিতে শব্দ খোঁজার মতো)  
  "ডিকশনারি খুলে প্রথমে মাঝখানটা দেখে, তারপর দুই দিকে গিয়ে শব্দ খোঁজা, এভাবেই তো সবার খোঁজ পাওয়া যায়!"
  
  **Pseudocode**:
  ```python
  def binary_search(arr, target):  # Changed 'list' to 'arr'
      low, high = 0, len(arr) - 1
      while low <= high:
          mid = (low + high) // 2
          if arr[mid] == target:
              return mid  # Found it!
          elif arr[mid] < target:
              low = mid + 1
          else:
              high = mid - 1
      return -1  # Not found
  ```

- **জাম্প সার্চ**: লাফিয়ে লাফিয়ে খোঁজা  
  "আপনি একটানা লাফ দিয়ে এগোচ্ছেন, এক এক করে দেখতে দেখতে মাঝখান পর্যন্ত পৌঁছে গেলেন। কিন্তু, লাফানো তো মজা!"
  
  **Pseudocode**:
  ```python
  def jump_search(arr, target):  # Changed 'list' to 'arr'
      import math
      n = len(arr)
      step = int(math.sqrt(n))  # Jump size
      prev = 0
      
      # Finding the block where element may be present
      while arr[min(step, n) - 1] < target:
          prev = step
          step += int(math.sqrt(n))
          if prev >= n:
              return -1  # Not found
              
      # Linear search in the identified block
      for i in range(prev, min(step, n)):
          if arr[i] == target:
              return i  # Found it!
      return -1  # Not found
  ```

- **হ্যাশিং**: ঠিকানা জেনে সরাসরি যাওয়া  
  "এটা যেমন একটা ঠিকানা জানা, আপনি সরাসরি সেখানে চলে যান। সময় নষ্ট করার কোন দরকার নেই, সোজা গন্তব্যে পৌঁছালেন!"
  
  **Pseudocode**:
  ```python
  def hash_search(hash_table, key):
      hash_index = hash_function(key)  # Calculate hash index
      if hash_table[hash_index] == key:
          return hash_index  # Found it!
      return -1  # Not found
  ```
  
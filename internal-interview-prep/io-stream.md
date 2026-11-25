## Stream

- So far, we have used FileWriter for writing text and Scanner for reading text. These are easy to use, but they are mainly designed for simple text files.
- I/O Streams are more flexible, because they work with text and binary data (like images, audio, PDFs).


## Choosing the Right Class
- Scanner - best for simple text and when you want to parse numbers or words easily.
- BufferedReader - best for large text files, because it is faster and reads line by line.
- FileInputStream - best for binary data (images, audio, PDFs) or when you need full control of raw bytes.
- FileOutputStream - best for binary data (images, PDFs, audio) or when you need full control of raw bytes.
- Scanner - best for simple text. It can split text into lines, words, or numbers (e.g., nextInt(), nextLine()).
- BufferedReader - best for large text files. It is faster, uses less memory, and can read full lines with readLine().
- FileInputStream - best for binary files (like images, PDFs, or audio)
- 

## Types of Streams

### Byte Streams
Work with raw binary data (like images, audio, and PDF files).
Examples: FileInputStream, FileOutputStream.


### Character Streams
Work with text (characters and strings). These streams automatically handle character encoding.
Examples: FileReader, FileWriter, BufferedReader, BufferedWriter.



## FileInputStream
- when reading binary data (like images, audio, or PDFs), or when you need full control of raw bytes. In those cases, you use FileInputStream.
Programming example is copy paste a file, reading whole files

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class CopyFile {
  public static void main(String[] args) {
    // Copy image.jpg into copy.jpg
    try (FileInputStream input = new FileInputStream("image.jpg");
         FileOutputStream output = new FileOutputStream("copy.jpg")) {

      int i;
      while ((i = input.read()) != -1) {
        output.write(i);  // write the raw byte to the new file
      }

      System.out.println("File copied successfully.");

    } catch (IOException e) {
      System.out.println("Error handling file.");
    }
  }
}
```

## FileOutputStream

see above example for this as well

## BufferedReader

BufferedReader and BufferedWriter make reading and writing text files faster.

- BufferedReader lets you read text line by line with readLine().
- BufferedWriter lets you write text efficiently and add new lines with newLine().

Ex:

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class Main {
  public static void main(String[] args) {
    try (BufferedReader br = new BufferedReader(new FileReader("filename.txt"))) {
      String line;
      while ((line = br.readLine()) != null) {
        System.out.println(line);
      }
    } catch (IOException e) {
      System.out.println("Error reading file.");
    }
  }
}
```

## BufferedWriter
The BufferedWriter class is used to write text to a file, one line or one string at a time. If the file already exists, its contents will be replaced (overwritten).

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class Main {
  public static void main(String[] args) {
    try (BufferedWriter bw = new BufferedWriter(new FileWriter("filename.txt"))) {
      bw.write("First line");
      bw.newLine();  // add line break
      bw.write("Second line");
      System.out.println("Successfully wrote to the file.");
    } catch (IOException e) {
      System.out.println("Error writing file.");
    }
  }
}
```
### Append to a Text File

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class Main {
  public static void main(String[] args) {
    // true = append mode
    try (BufferedWriter bw = new BufferedWriter(new FileWriter("filename.txt", true))) {
      bw.newLine();                      // move to a new line
      bw.write("Appended line");         // add new text at the end
      System.out.println("Successfully appended to the file.");
    } catch (IOException e) {
      System.out.println("Error writing file.");
    }
  }
}
```

Final Tips:

1. Jab aap FileWriter use karte hain: Aap already Character Stream use kar rahe hain. Yeh characters (A, B, C, 1, 2, 3) ko seedha file mein bhejta hai.
2. Jab aap FileOutputStream use karte hain: Tab aap Byte Stream use karte hain. Yeh data ko raw bytes (0 aur 1) mein badal kar file mein bhejta hai.



FileWriter vs BufferedWriter (Comparison)


# Java File Handling, Streams & Buffer — Quick Notes

## 1. Core Concepts Ka Fark

| Concept | Asli Matlab | Main Kaam | Important Java Classes |
| :--- | :--- | :--- | :--- |
| **File Handling** | File/Folder ka address aur structure manage karna. | File create, delete, rename, aur size/existence check karna. | `File`, `Path`, `Files` |
| **Stream** | Data ke travel karne ka rasta (pipeline). | Program aur file ke beech data read/write karna. | `InputStream`, `OutputStream`, `Reader`, `Writer` |
| **Buffer** | RAM mein temporary storage area (trolley). | Ek-ek byte ke bajay bada chunk transfer karke speed badhana. | `BufferedReader`, `BufferedWriter`, `BufferedInputStream` |

---

## 2. Java Streams Ke Types (Kab Kya Use Karein?)

| Stream Type | Kis Data Ke Liye? | Read Karne Ki Class | Write Karne Ki Class | Special Feature / Use Case |
| :--- | :--- | :--- | :--- | :--- |
| **Byte Stream** | Images, Audio, Video, PDF (`.jpg`, `.mp3`, `.pdf`) | `FileInputStream` | `FileOutputStream` | Data ko raw bytes (`0` aur `1`) mein transfer karta hai. |
| **Character Stream** | Plain Text Files (`.txt`, `.csv`, `.java`) | `FileReader` | `FileWriter` | Seedha characters/text read aur write karta hai (slow for large files). |
| **Buffered Character Stream** | Badi Text Files (Fast Performance) | `BufferedReader` | `BufferedWriter` | RAM buffer (8 KB) use karta hai. `readLine()` aur `newLine()` methods milte hain. |
| **Buffered Byte Stream** | Badi Media/Binary Files (Fast Performance) | `BufferedInputStream` | `BufferedOutputStream` | Badi files ko copy ya transfer karte waqt speed bahut fast rakhta hai. |

---

## 3. Golden Rules (Yaad Rakhne Wali Baatein)
* **`File` class** sirf file ka **path/container** batati hai, data read/write nahi karti.
* **`Buffered` classes** akeli kaam nahi kartin—inhone hamesha normal stream (`FileReader`/`FileWriter`) ko wrap karna hota hai.
* **`close()` ya `flush()`** call karna zaroori hai, warna buffer (RAM) ka data hard disk par save nahi hoga.


• Jab buffer bhar jaata hai, ya jab aap bw.close() ya bw.flush() call karte hain, tabhi saara data ek saath hard disk ki file mein save hota hai. Agar close() bhool gaye, toh file khaali reh sakti hai.

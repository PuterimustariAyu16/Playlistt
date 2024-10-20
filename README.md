public class Song {
    String title;
    Song next;

    // Constructor untuk inisialisasi objek Song
    public Song(String title) {
        this.title = title;
        this.next = null;
    }
}
public class Playlist {
    private Song head; // Head dari linked list untuk playlist

    // Menambahkan lagu ke akhir playlist
    public void addSong(String title) {
        Song newSong = new Song(title);

        // Jika playlist masih kosong, set lagu pertama sebagai head
        if (head == null) {
            head = newSong;
        } else {
            Song temp = head;
            while (temp.next != null) {
                temp = temp.next;
            }
            temp.next = newSong; // Tambah lagu di akhir
        }
    }

    // Menampilkan semua lagu dalam playlist
    public void displayPlaylist() {
        if (head == null) {
            System.out.println("Playlist kosong.");
            return;
        }

        Song temp = head;
        while (temp != null) {
            System.out.println("Lagu: " + temp.title);
            temp = temp.next;
        }
    }
}
public class main {
    public static void main(String[] args) {
        Playlist playlist = new Playlist();

        // Menambah lagu ke playlist
        playlist.addSong("kejar mimpi - Maudy Ayunda");
        playlist.addSong("Saya Pasti Bisa - Saykoji ft Merry Riana");
        playlist.addSong("Manusia Kuat - Tulus");
        playlist.addSong("Taklukkan Dunia - Noxcy");


        // Menampilkan playlist
        System.out.println("Playlist Anda:");
        playlist.displayPlaylist();
    }
}


<script>
export default {
    props: ['nama', 'umur'],
    data() {
        return {
            pesan: 'Halo, ' + this.nama + '!'
        };
    },
    methods: {
        greet() {
            console.log('Halo, bro!');
        }
    },
    computed: {
        pesanSelamat() {
            return 'Selamat datang, ' + this.nama + '!';
        }
    },
    watch: {
        umur(newUmur, oldUmur) {
            console.log('Umur berubah dari', oldUmur, 'menjadi', newUmur);
            // Lakukan tindakan responsif lainnya...
        }
    }
}
</script>
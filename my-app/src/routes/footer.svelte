<footer>
    <div class="footercontainer">
        <div class="socialicons">
            <a href=""><i class="fa-brands fa-instagram"></i></a>
            <a href=""><i class="fa-brands fa-facebook"></i></a>
        </div>
        <div class="footerNav">
            <ul>
                <li><a href="">Home</a></li>
                <li><a href="">News</a></li>
                <li><a href="">About</a></li>
                <li><a href="">Contact Us</a></li>
                <li><a href="">Our Team</a></li>
            </ul>
        </div>
        <div class="footerBottom">
            <p>Copyright &copy;2024; Designed by <span class="designer">Krotify</span></p>
        </div>
    </div>
</footer>
<style>
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
footer{
    background-color: #111;
}
.footercontainer{
    width: 100%;
    padding: 70px 30px 20px;
}
.socialicons{
    display: flex;
    justify-content: center;
}
.socialicons a{
    text-decoration: none;
    padding: 10px;
    background-color: white;
    margin: 10px;
    border-radius: 100%;
}

.socialicons a i{
    font-size: 2em;
    color: black;
    opacity: 0.9;
}

/* Hover Effects on Social Media Icons */
.socialicons a:hover{
    background-color: #111;
    transition: 0.5s;
}

.socialicons a:hover i{
    color: white;
    transition: 0.5s;
}
.footerNav{
    margin: 30px 0;
}
.footerNav ul{
    display: flex;
    justify-content: center;
    list-style-type: nonedisc;
}
.footerNav ul li a{
    color: white;
    margin: 20px;
    text-decoration: none;
    font-size: 1.3em;
    opacity: 0.7;
    transition: 0.5s;
}
.footerNav ul li a:hover{
    opacity: 1;
}
.footerBottom{
    padding: 20px;
    text-align: center;
}
.footerBottom p{
    color: white;
}
.designer{
    opacity: 0.7;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: 400;
    margin: 0px 5px;
}
@media (max-width: 700px){
    .footerNav ul{
        flex-direction: column;
    }
    .footerNav ul li{
        width: 100%;
        text-align: center;
        margin: 10px;
    }
}
</style>
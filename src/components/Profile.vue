<template>
    <div>
        <div class="row">
            <div class="col-md-4">
                <div class="card" style="width: 18rem;">
                    <img class="card-img-top" :src="user.avatar_url" >
                    <ul class="list-group list-group-flush">
                        <li class="list-group-item">
                            Nome:
                            <span class="badge">{{ user.name }}</span>
                        </li>
                        <li class="list-group-item">
                            Bio:
                            <span class="badge">{{ user.bio }}</span>
                        </li>
                        <li class="list-group-item">
                            Email:
                            <span class="badge">{{ user.email }}</span>
                        </li>
                        <li class="list-group-item">
                            Localisação:
                            <span class="badge">{{ user.location }}</span>
                        </li>
                        <li class="list-group-item">
                            Repositórios: 
                            <span class="badge badge-success">{{ user.public_repos }}</span>
                        </li>
                        <li class="list-group-item">
                            Seguidores:
                            <span class="badge badge-primary">{{ user.followers }}</span>
                        </li>
                        <li class="list-group-item">
                            Seguindo:
                            <span class="badge badge-info">{{ user.following }}</span>
                        </li>
                        
                    </ul>
                    <div class="card-body">
                        <a target="blanck" :href="user.html_url" class="btn btn-success btn-block">Ver Perfil</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['user']
}
</script>

<style>

</style>

# gerenciamento-de-um-cat-logo-de-jogos
PARTE HTML categorias:
<h2>Lista de Jogos</h2>
<table>
  <thead>
    <tr>
      <th>Título</th>
      <th>Descrição</th>
      <th>Data de Lançamento</th>
      <th>Gênero(s)</th>
      <th>Desenvolvedora</th>
    </tr>
  </thead>
  <tbody>
    <tr *ngFor="let game of games">
      <td>{{ game.title }}</td>
      <td>{{ game.description }}</td>
      <td>{{ game.releaseDate }}</td>
      <td>{{ game.genres.join(', ') }}</td>
      <td>{{ game.developer }}</td>
    </tr>
  </tbody>
</table>

serviço que consome API REST:

import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
import { Game } from './game.model';

@Injectable({
  providedIn: 'root'
})
export class GameService {
  private apiBaseUrl = 'http://localhost:3000/api/games';

  constructor(private http: HttpClient) { }

  getGames(): Observable<Game[]> {
    return this.http.get<Game[]>(this.apiBaseUrl);
  }
}

Modelo para representar os jogos: 

export interface Game {
  id: number;
  title: string;
  description: string;
  releaseDate: Date;
  genres: string[];
  developer: string;
}
dificuldades:
Não sei criar o componente que usaria GameService para recuperar os jogos e exibi-los na tela.

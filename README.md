# Celestial_bodys
--
-- PostgreSQL database dump
--

-- Dumped from database version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)
-- Dumped by pg_dump version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

DROP DATABASE universe;
--
-- Name: universe; Type: DATABASE; Schema: -; Owner: freecodecamp
--

CREATE DATABASE universe WITH TEMPLATE = template0 ENCODING = 'UTF8' LC_COLLATE = 'C.UTF-8' LC_CTYPE = 'C.UTF-8';


ALTER DATABASE universe OWNER TO freecodecamp;

\connect universe

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

SET default_tablespace = '';

SET default_table_access_method = heap;

--
-- Name: galaxy; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.galaxy (
    galaxy_id integer NOT NULL,
    name character varying(30) NOT NULL,
    description numeric NOT NULL,
    numero integer NOT NULL,
    life double precision NOT NULL,
    comida character varying(30) NOT NULL
);


ALTER TABLE public.galaxy OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_galaxy_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_galaxy_id_seq OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_galaxy_id_seq OWNED BY public.galaxy.galaxy_id;


--
-- Name: moon; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.moon (
    moon_id integer NOT NULL,
    name character varying(30) NOT NULL,
    description boolean NOT NULL,
    life double precision NOT NULL,
    numero integer NOT NULL,
    planet_id integer
);


ALTER TABLE public.moon OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.moon_moon_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.moon_moon_id_seq OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.moon_moon_id_seq OWNED BY public.moon.moon_id;


--
-- Name: new_table; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.new_table (
    new_table_id integer NOT NULL,
    name character varying(30) NOT NULL,
    description character varying(30) NOT NULL
);


ALTER TABLE public.new_table OWNER TO freecodecamp;

--
-- Name: new_table_new_table_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.new_table_new_table_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.new_table_new_table_id_seq OWNER TO freecodecamp;

--
-- Name: new_table_new_table_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.new_table_new_table_id_seq OWNED BY public.new_table.new_table_id;


--
-- Name: planet; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.planet (
    planet_id integer NOT NULL,
    name character varying(30) NOT NULL,
    description boolean NOT NULL,
    numero integer NOT NULL,
    life double precision NOT NULL,
    star_id integer
);


ALTER TABLE public.planet OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.planet_planet_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.planet_planet_id_seq OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.planet_planet_id_seq OWNED BY public.planet.planet_id;


--
-- Name: star; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.star (
    star_id integer NOT NULL,
    name character varying(30) NOT NULL,
    description text NOT NULL,
    galaxy_id integer,
    life double precision NOT NULL
);


ALTER TABLE public.star OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.star_star_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.star_star_id_seq OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.star_star_id_seq OWNED BY public.star.star_id;


--
-- Name: galaxy galaxy_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy ALTER COLUMN galaxy_id SET DEFAULT nextval('public.galaxy_galaxy_id_seq'::regclass);


--
-- Name: moon moon_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon ALTER COLUMN moon_id SET DEFAULT nextval('public.moon_moon_id_seq'::regclass);


--
-- Name: new_table new_table_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.new_table ALTER COLUMN new_table_id SET DEFAULT nextval('public.new_table_new_table_id_seq'::regclass);


--
-- Name: planet planet_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet ALTER COLUMN planet_id SET DEFAULT nextval('public.planet_planet_id_seq'::regclass);


--
-- Name: star star_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star ALTER COLUMN star_id SET DEFAULT nextval('public.star_star_id_seq'::regclass);


--
-- Data for Name: galaxy; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.galaxy VALUES (2, 'andromeda', 2, 3, 1, 'hola');
INSERT INTO public.galaxy VALUES (4, 'camila', 3, 1, 2, 'potato');
INSERT INTO public.galaxy VALUES (5, 'lacto', 1, 6, 8, 'lampara');
INSERT INTO public.galaxy VALUES (6, 'lactos', 3, 5, 10, 'lamparas');
INSERT INTO public.galaxy VALUES (7, 'lactots', 9, 4, 123, 'lamparasz');
INSERT INTO public.galaxy VALUES (8, 'lactots', 9, 4, 1233, 'lamparasz');


--
-- Data for Name: moon; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.moon VALUES (1, 'pablo', true, 12, 1, 2);
INSERT INTO public.moon VALUES (3, 'pablo', true, 1, 2, 2);
INSERT INTO public.moon VALUES (4, 'pablo', true, 2, 2, 2);
INSERT INTO public.moon VALUES (5, 'pablo', true, 3, 2, 2);
INSERT INTO public.moon VALUES (6, 'pablo', true, 4, 2, 2);
INSERT INTO public.moon VALUES (7, 'pablo', true, 5, 2, 2);
INSERT INTO public.moon VALUES (8, 'pablo', true, 6, 2, 2);
INSERT INTO public.moon VALUES (9, 'pablo', true, 7, 2, 2);
INSERT INTO public.moon VALUES (10, 'pablo', true, 8, 2, 2);
INSERT INTO public.moon VALUES (11, 'pablo', true, 9, 2, 2);
INSERT INTO public.moon VALUES (12, 'pablo', true, 10, 2, 2);
INSERT INTO public.moon VALUES (13, 'pablo', true, 11, 2, 2);
INSERT INTO public.moon VALUES (15, 'pablo', true, 13, 2, 2);
INSERT INTO public.moon VALUES (16, 'pablo', true, 14, 2, 2);
INSERT INTO public.moon VALUES (17, 'pablo', true, 15, 2, 2);
INSERT INTO public.moon VALUES (18, 'pablo', true, 16, 2, 2);
INSERT INTO public.moon VALUES (19, 'pablo', true, 17, 2, 2);
INSERT INTO public.moon VALUES (20, 'pablo', true, 18, 2, 2);
INSERT INTO public.moon VALUES (21, 'pablo', true, 19, 2, 2);
INSERT INTO public.moon VALUES (22, 'pablo', true, 20, 2, 2);


--
-- Data for Name: new_table; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.new_table VALUES (1, 'pedro', '2');
INSERT INTO public.new_table VALUES (4, 'pedros', '3');
INSERT INTO public.new_table VALUES (7, 'pedrosd', '1');


--
-- Data for Name: planet; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.planet VALUES (2, 'qw', true, 2, 3, 2);
INSERT INTO public.planet VALUES (4, 'qw', true, 2, 4, 2);
INSERT INTO public.planet VALUES (5, 'qw', true, 2, 5, 2);
INSERT INTO public.planet VALUES (6, 'qw', true, 2, 0, 2);
INSERT INTO public.planet VALUES (7, 'qw', true, 2, 45, 2);
INSERT INTO public.planet VALUES (8, 'qw', true, 2, 676, 2);
INSERT INTO public.planet VALUES (9, 'qw', true, 2, 8978, 2);
INSERT INTO public.planet VALUES (10, 'qw', true, 2, 123213, 2);
INSERT INTO public.planet VALUES (11, 'qw', true, 2, 56, 2);
INSERT INTO public.planet VALUES (12, 'qw', true, 2, 98, 2);
INSERT INTO public.planet VALUES (13, 'qw', true, 2, 12312333, 2);
INSERT INTO public.planet VALUES (14, 'qw', true, 2, 55, 2);


--
-- Data for Name: star; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.star VALUES (2, 'pedro', 'banana', 2, 3);
INSERT INTO public.star VALUES (4, 'juan', 'cabe', 4, 4);
INSERT INTO public.star VALUES (5, 'juany', 'cabez', 5, 1);
INSERT INTO public.star VALUES (7, 'juand', 'cabe', 5, 23);
INSERT INTO public.star VALUES (8, 'juand', 'cabe', 6, 233);
INSERT INTO public.star VALUES (9, 'juand', 'cabe', 7, 2313);
INSERT INTO public.star VALUES (10, 'juand', 'cabe', 8, 22313);


--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_galaxy_id_seq', 8, true);


--
-- Name: moon_moon_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.moon_moon_id_seq', 22, true);


--
-- Name: new_table_new_table_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.new_table_new_table_id_seq', 7, true);


--
-- Name: planet_planet_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.planet_planet_id_seq', 14, true);


--
-- Name: star_star_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.star_star_id_seq', 10, true);


--
-- Name: galaxy galaxy_life_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_life_key UNIQUE (life);


--
-- Name: galaxy galaxy_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_pkey PRIMARY KEY (galaxy_id);


--
-- Name: moon moon_life_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_life_key UNIQUE (life);


--
-- Name: moon moon_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_pkey PRIMARY KEY (moon_id);


--
-- Name: new_table new_table_description_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.new_table
    ADD CONSTRAINT new_table_description_key UNIQUE (description);


--
-- Name: new_table new_table_name_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.new_table
    ADD CONSTRAINT new_table_name_key UNIQUE (name);


--
-- Name: new_table new_table_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.new_table
    ADD CONSTRAINT new_table_pkey PRIMARY KEY (new_table_id);


--
-- Name: planet planet_life_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_life_key UNIQUE (life);


--
-- Name: planet planet_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_pkey PRIMARY KEY (planet_id);


--
-- Name: star star_life_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_life_key UNIQUE (life);


--
-- Name: star star_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_pkey PRIMARY KEY (star_id);


--
-- Name: moon moon_planet_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_planet_id_fkey FOREIGN KEY (planet_id) REFERENCES public.planet(planet_id);


--
-- Name: planet planet_star_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_star_id_fkey FOREIGN KEY (star_id) REFERENCES public.star(star_id);


--
-- Name: star star_galaxy_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_galaxy_id_fkey FOREIGN KEY (galaxy_id) REFERENCES public.galaxy(galaxy_id);


--
-- PostgreSQL database dump complete
--


